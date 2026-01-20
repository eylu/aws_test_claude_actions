<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/contact">Contact</router-link>
    </nav>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style scoped>
nav {
  padding: 20px;
  background-color: #f0f0f0;
  margin-bottom: 20px;
}

nav a {
  margin-right: 15px;
  text-decoration: none;
  color: #42b983;
  font-weight: bold;
}

nav a:hover {
  text-decoration: underline;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
