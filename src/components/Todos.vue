<template>
   <div>
   <ul v-for="todo in todos" :key="todo.id">
     <li v-if="todo.userId == 2 && todo.completed == true">

        <p> <strong>Id: </strong> {{ todo.id }} </p> 
        <p> <strong>Title: </strong> {{todo.title }}</p>
        <p> <strong>Completed: </strong> {{todo.completed }}</p> <br>

     </li>
   </ul>
   
   <h3>Recupere e mostre todos os dados do usuário 2 e estão com status de completo em
uma lista</h3>

   <button @click="fetchTodos">Fetch Todos</button>
 </div>
</template>

<script>
export default {
    name: "Todos",
 data() {
   return {
     todos: [],
     baseURI: "https://jsonplaceholder.typicode.com/todos"
   };
 },
 
 methods: {
  fetchTodos: function() {
     this.$http.get(this.baseURI).then((result) => {
       this.todos = result.data;
     });
   },
 },
};
</script>

<style>

</style>