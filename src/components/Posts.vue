<template>
  <div>
   <ul v-for="post in posts" :key="post.albumId ">
     <li v-if="post.userId %2 == 1">

       <p> <strong>Id:</strong> {{post.id}} </p>
       <p> <strong>Title:</strong> {{post.title}} </p>
       <p> <strong>Body:</strong> {{post.body}} </p> <br>

     </li>
   </ul>
   

   <button @click="fetchPosts">Fetch Posts</button>
 </div>
</template>

<script>
export default {
name: "Posts",
 data() {
   return {
     posts: [],
     baseURI: "https://jsonplaceholder.typicode.com/posts"
   };
 },
 methods: {
   fetchPosts: function() {
     this.$http.get(this.baseURI).then((result) => {
       this.posts = result.data;
     });
   },
 },

};
</script>

<style>

</style>