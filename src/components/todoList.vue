<template>
  <div>
      <p>Completed tasks: {{todos.filter(todo =>{return todo.done === true}).length}}</p>
      <p>Inompleted tasks: {{todos.filter(todo =>{return todo.done === false}).length}}</p>
      <todo v-for="todo in todos"  v-bind:key="todo.id" v-bind:todo="todo" v-on:delete-todo="deleteTodo"></todo>
  </div>
</template>

<script type ="text/javascript">
import todo from './todo'
export default {
    components:{
        todo
    },
    props:["todos"],
    methods:{
        deleteTodo(todo){
        const todoIdx = this.todos.indexOf(todo);
        this.todos.splice(todoIdx, 1);
        }
    }
};
</script>
<style>

</style>
