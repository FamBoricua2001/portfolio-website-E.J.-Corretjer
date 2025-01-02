<template>
  <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    <router-view/>
  </nav>
  <Repositories />
</template>

<script>
import Repositories from './components/Repositories.vue';

export default {
  name: 'App',
  components: {
    Repositories
  }
}</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: lightblue;
  text-decoration: none;
  padding: 10px;
  border-radius: 4px
}

nav a:hover {
  color: red;
}

nav a.router-link-exact-active {
  color: gray;
  background: black;

}
</style>
