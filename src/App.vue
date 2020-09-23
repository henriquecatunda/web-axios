<template>
  <div id="app">
    <div id="nav">
      <router-link style="text-decoration: none"  to="/">Users</router-link> |
      <router-link style="text-decoration: none" to="/todos">Todos</router-link> |
      <router-link style="text-decoration: none" to="/photos">Photos</router-link> |
      <router-link style="text-decoration: none" to="/comments">Comments</router-link> |
      <router-link style="text-decoration: none" to="/posts">Posts</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

</style>
