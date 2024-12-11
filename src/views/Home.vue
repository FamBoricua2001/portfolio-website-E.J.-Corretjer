<template>
  <div class="Home">
    <img class="profile-pic" alt="Pro Pic" :src="require('@/assets/ecorretjerlandi.png')">
    <Title msg="E.J. Corretjer"/>
  </div>
</template>

<script>
import Title from '@/components/Title.vue';

export default
{
  name: 'Home',
  components:
  {
    Title
  }
}
</script>

<style scope>
.profile-pic 
{
  padding: 50px;
}
</style>