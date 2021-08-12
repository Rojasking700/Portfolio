<template>
  <div class="app">
    <Nav/>
  </div>
  <router-view/>
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
  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
</style>
