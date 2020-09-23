<template>
  <div>
   <ul v-for="user in users" :key="user.id ">
     <li v-if="user.id <= 5 ">

       <p> <strong>Id: </strong> {{user.id}}</p>
       <p> <strong>Name: </strong> {{ user.name }}</p>
       <p> <strong>Username: </strong> {{ user.username }}</p>
       <p> <strong>Email: </strong> {{ user.email }}</p>
       <p> <strong>Address: </strong> {{ user.address }}</p>
       <p> <strong>Phone: </strong>  {{ user.phone }}</p>
       <p> <strong>Website: </strong> {{ user.website }}</p>
       <p> <strong>Company: </strong> {{ user.company}}</p> <br>
        
     </li>
   </ul>
  

   <button @click="fetchUsers">Fetch Users</button>
 </div>

</template>

<script>
export default {
 name: "Users",
 data() {
   return {
     users: [],
     baseURI: "https://jsonplaceholder.typicode.com/users"
   };
 },
 methods: {
   fetchUsers: function() {
     this.$http.get(this.baseURI).then((result) => {
       this.users = result.data;
     });
   },
 },
};

</script>

<style>

button {

  width: 140px;
  height: 35px;
  background-color: black;
  color: white;
  border-radius: 4px;
  cursor: pointer;
}
</style>