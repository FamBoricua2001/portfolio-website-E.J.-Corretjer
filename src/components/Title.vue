<template>
  <div class="Hello">
    <h1>{{msg}}</h1>
    <p>My name is E.J. Corretjer I am in the progress of obtaining an associates degree in Infomation Technology with a concentration in Web Debelopment.  I really enjoy working on websites, creating applications and trying to find solutions to problems and prevent problems before they start.  I have always had an interest in all kinds of technology.  I would like to use my new skills in Cyber Security or helping clients create applications or websites that meet their needs.</p>
  </div>
</template>

<script>
export default {
  name: 'Title',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3
{
  margin: 40px 0 0;
  text-decoration-color: midnightblue;
}
p
{
  text-align: left;
  font-style: italic;
}
</style>