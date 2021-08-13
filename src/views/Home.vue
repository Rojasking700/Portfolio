<template>
  <section>
    <div class="home">
      <Landing class="Landing"/>
      <Iam class="Iam"/>
    </div>

  </section>
</template>

<script>
// import gsap from 'gsap'
import Iam from '../components/Iam.vue';
import Landing from '../components/Landing.vue';

export default {
  name: 'Home',
  components: {
    Landing,
    Iam
  }

    
}
</script>
