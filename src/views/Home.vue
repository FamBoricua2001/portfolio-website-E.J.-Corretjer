<template>
  <div class="Home">
    <img alt="Picture of Me" src="/assets/ejcorretjerlandi.png">
    <Title msg="E.J. Corretjer"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Title from '@/components/Title.vue';

export default {
  name: 'Home',
  components: {
    Title
  }
}
</script>
