<template>
  <div class="Home">
    <img alt="Pro Pic" :src="require('@/assets/ecorretjerlandi.png')">
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