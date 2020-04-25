<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <img v-bind:title="logoTitle" alt="Vue logo" src="./assets/logo.png">
    <HelloWorld v-if="false" msg="Welcome to Your Vue.js App"/>
    <p v-if="true">Now you see me!</p>
    <ol>
      <li v-bind:key="idx" v-for="(todo, idx) in todos">{{ todo }}</li>
    </ol>
    <button v-on:click="addTodo">Add Todo</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'



export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data: function() {
    return {
      title: 'Headfirst VueJS',
      logoTitle: "This is Vue logo",
      todos: [
        { text: 'Learn JavaScript' },
        { text: 'Learn Vue' },
        { text: 'Build something awesome' },      
      ]
    }
  },
  methods: {
    addTodo(){
      this.todos.push({'text': 'Vue fundamental'})
    },
  },
  beforeCreate: function(){
    console.info('beforeCreate')
    console.log(this.$el);  
    console.log(typeof this.$data)
  },
  created: function(){
    console.info('created')
    console.log(this.$el)  
    console.log(this.$data)
  },
  beforeMount: function(){
    console.info('beforeMount')
    console.log(this.$data)
    console.log(this.$el)  
  },
  mounted: function(){
    console.info('mount')
    console.log(this.$data)
    console.log(this.$el) 
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
}
</style>
