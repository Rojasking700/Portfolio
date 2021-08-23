<template>
<main id='app' >
  <div class="app">
    <Nav/>
  </div>
  <router-view/>
</main>
</template>

<script>
import Nav from './components/Nav.vue'
export default {
  name: "App",
  components: {
    Nav,
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Fjalla+One&display=swap');
  *{
    font-family: 'Fjalla One', sans-serif;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
</style>
