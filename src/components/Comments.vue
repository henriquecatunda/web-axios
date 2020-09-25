<template>
  <div class="Comments">
   <ul v-for="comment in comments" :key="comment.id ">
     <li v-if="comment.id %2 == 0">

        <p> <strong>postId</strong> {{ comment.postId }}</p>
        <p> <strong>Id:</strong>   {{comment.id }}</p>
        <p> <strong>Name: </strong>  {{comment.name }}</p>
        <p> <strong>Email:</strong>  {{comment.email }}</p>
        <p> <strong>Body: </strong>  {{comment.body }}</p> <br>

     </li>
   </ul>

   <h3>Recupere todos os registros e mostre todos os dados dos comentários pares em
uma lista</h3>
  
   <button @click="fetchComments">Fetch Comments</button>
 </div>
</template>

<script>
export default {
name: "Comments",
 data() {
   return {
     comments: [],
     baseURI: "https://jsonplaceholder.typicode.com/comments"
   };
 },
 methods: {
   fetchComments: function() {
     this.$http.get(this.baseURI).then((result) => {
       this.comments = result.data;
     });
   },
 },

}
</script>

<style>

li {
 text-align: left;
}
</style>