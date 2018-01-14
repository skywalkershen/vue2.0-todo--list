<template>
  <div id="app">
    <create-todo v-on:create-todo="addTodo"></create-todo>
    <todo-list v-bind:todos="todos"></todo-list>
    
    
  </div>
</template>

<script>

import todoList from './components/todoList'
import createTodo from './components/createTodo'

export default {
  name: 'app',
  components: {
    todoList,
    createTodo,
  },
  data(){
    return{
      todos:[
      {
        title: "hone skill 1",
        project: "practice js",
        done: false,
        id: 1
      },
      {
        title: "hone skill 2",
        project: "practice framework",
        done: false,
        id: 2
      },
      {
        title: "send the gift",
        project: "as the title explained",
        done: false,
        id: 3
      }]
    }
  },
  methods: {
    addTodo(newTodo){
      this.todos.push({
        title:newTodo.title,
        project: newTodo.project,
        done:newTodo.done,
        id: this.todos.length,

      });
    },
  },
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
