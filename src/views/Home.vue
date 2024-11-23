<template>
  <div class="Home">
    <img alt="Picture of Me" src="/assets/ejcorretjerlandi.png">
    <HelloWorld msg="E.J. Corretjer"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/Title.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>
