<template>
  <div id="app">
    <Header/>
    <Addtodo v-on:add-Todo ="addTodo"/>
   <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/Layout/Header';
import Todos from './components/Todos';
import Addtodo from './components/Addtodo'
export default {

  name: 'App',
  components: {
    Header,
    Todos,
    Addtodo
  },
  data(){
    return{
      todos:[
        {id:1,
        title: "iron chlothed",
        completed:true},
        {id:2,
        title:"learn Vue",
        completed:false},
        {id:3,
        title:"Watcg united",
        completed:true}
      ]
    }
  },
  methods:{
    deleteTodo(id){
this.todos = this.todos.filter(todo => todo.id !=id );
    },
    addTodo(newTodo){
      this.todos =  [...this.todos, newTodo]; 
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding:0;
}
body{
  font-family:Arial, Helvetica, sans-serif;
line-height: 1.4;
}

.btn{
  display: inline-block;
  border: none;
  background: #555;
  color:#fff;
  padding: 7px 20px;
  cursor: pointer;

}

.btn:hover{
  background: #666;
}


</style>
