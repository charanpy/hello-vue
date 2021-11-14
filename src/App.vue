<template @keyup.ctrl.alt="ctrlAlt()">
  <img alt="Vue logo" src="./assets/logo.png" @keyup.left="mouse()">
  <HelloWorld :msg="message"/>
  <p :style="{color: getColor}">{{isReact}}</p>
  <p>
    <input v-model="language" placeholder="Fav lang" />
  </p>
  <p v-show="!!language">
    My Fav Lang is {{language}}
  </p>
  <button @click="click()">Click</button>
  <button @click="toggleShow()">Toggle</button>

  <br />
  <p>{{count}}</p>
  <Increment @incrementCount="incrementCount" />
  <Language name="ReactJS" about="React is JS library" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Language from './components/Language.vue'
import Increment from './components/Incremrnt.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Language,
    Increment
  },
  data: function() {
    return {
      message:"Hello Vue",
      show: false,
      language:"",
      count:0
    }
  },
  methods: {
    click(){
      this.message = "Hello react"
    },
    toggleShow() {
      this.show = !this.show
    },
    keyup(){
      console.log('Key up')
    },
    ctrlAlt() {
      console.log('Ctrl alt')
    },
    mouse() {
      console.log("mouse");
    },
    incrementCount(){
      this.count = this.count+1
    }
  },
  computed: {
    isReact() {
      return this.message.includes('react') ? "React is Awesome" : ""
    },
    getColor() {
      return this.show ? 'red' : 'black'
    }
  }
 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  line-height: 1.7;
}

button {
  width:100px;
  padding: 6px;
  background: #2c3e50;
  color: white;
  border: none;
  outline: none;
  border-radius: 5px;
  margin-right: 1rem;
  cursor: pointer;
}
</style>
