<template>
  <div class="Photos">
   <ul v-for="photo in photos" :key="photo.id ">
     <li v-if="photo.albumId == 3">

         <img :src="photo.url" alt="photo">

     </li>
   </ul>
   
   <h3>Recupere e mostre todas as imagens (url) do álbum 3 em uma lista</h3>

   <button @click="fetchPhotos">Fetch Photos</button>
 </div>
</template>

<script>
export default {
name: "Photos",
 data() {
   return {
     photos: [],
     baseURI: "https://jsonplaceholder.typicode.com/photos"
   };
 },
 methods: {
   fetchPhotos: function() {
     this.$http.get(this.baseURI).then((result) => {
       this.photos = result.data;
     });
   },
 },
};

</script>

<style>

.Photos li {
 text-align: center;
 
}


</style>