<template>
  <div class="home">
    <Landing/>
    <Iam />
  </div>
  <section>

  </section>
  </template>

<script>
import Iam from '../components/Iam.vue'
import Landing from '../components/Landing.vue'
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    Landing,
    Iam
    
  }
}
</script>
