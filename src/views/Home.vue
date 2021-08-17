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
import Iam from '../components/Home/Iam.vue';
import Landing from '../components/Home/Landing.vue';

export default {
  name: 'Home',
  components: {
    Landing,
    Iam
  }

    
}
</script>
