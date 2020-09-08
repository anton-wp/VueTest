<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from '@/page/home'

export default {
  name: 'App',
  components: {
    Home,
  },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');

body {
  margin: 0;
}
#app {
  padding: 20px 20px 0;
  font-family: 'Lato', sans-serif;
  background-color: #f1f1f1;
  height: 1000px;
  //font-family: 'Montserrat', sans-serif;
}
</style>
