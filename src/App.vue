<template>
  <div id="app">
    <skills />
  </div>
</template>

<script>
import skills from './components/skills.vue'

export default {
  name: 'App',
  components: {
    skills
  }
}
</script>

<style>
@import url(https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,700;1,300;1,400&display=swap);

body {
background-color: #eee;
font-family: 'Monserrat', sans-serif;
   display: grid;
  grid-template-rows: auto;
  justify-items: center;
  align-items: center;
}

#app {
 
  width: 50%;
 
}
body, html {
  margin: 0;
  height: 100%;
}

</style>
