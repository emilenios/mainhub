<template>
  <div>
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>

import axios from 'axios';
import AddTodo from '../components/AddTodo';
import Todos from '../components/Todos';
export default {
  name :'Home',
  components: {
    Todos,
    AddTodo
  },
  data(){
    return{
      todos: []

    }
  },
  methods: {
    deleteTodo(id){
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`).then(this.todos = this.todos.filter(todo => todo.id !== id))

      //this.todos = this.todos.filter(todo => todo.id !== id);

    },
    addTodo(newTodo){
      const { title, completed} = newTodo;
      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title, completed
        })
          .then( res => this.todos = [...this.todos, res.data])
          
      
    }
  },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=4').then(res => this.todos = res.data)

  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;


  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn{
    display: inline-block;
    border: none;
    background: #555;
    color: aliceblue;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover{

    background: #777;
  }

</style>
