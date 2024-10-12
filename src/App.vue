<template>
  <div>
    <img src="ecorretjerlandi.jpg" alt="Profile Picture">
    <h1>{{title}}</h1>
    <h3>{{title1}}</h3>
    <Discription />
  </div>
</template>

<script>
import Discription from './components/Discription.vue'


export default {
  name: 'App',
  components: {
    Discription
  },
  data() {
    return {
      imageSrc: ('./assets/ecorretjerlandi.jpg'),
      title: 'E.J. Corretjer',
      title1: 'Web Developer'
    }
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
  margin-top: 60px;
}
h1 {
  border-bottom: 2px solid black;
  display: inline-block;
  padding-bottom: 10px;
}
img {
  max-width: 100%;
  height: auto;
  margin-top: 20px;
}
</style>
