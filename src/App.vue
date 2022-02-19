<template>
  <div id="nav">
    <router-link :class="{ active: $route.name === 'Home' }" to="/">Home</router-link> |
    <router-link :class="{ active: $route.name === 'Cart' }" to="/cart">Cart</router-link>
  </div>
  <router-view />
</template>


<script>
  export default{
    mounted(){
      this.$store.commit('updateCartFromLocalStorage')
    }
  }
</script>
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

html,
body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

body {
  background-color: rgba(245, 245, 245);
}

a {
  font-weight: bold;
  color: darkgray;
  text-decoration: none;
  margin: 0 5px 0 5px;
  font-size: 1.25rem;
}
a:active {
  color: #2c3e50;
}

.text-center {
  text-align: center;
}
</style>
