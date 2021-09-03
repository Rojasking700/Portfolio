<template>
<main id='app' >
  <div class="app">
    <Nav/>
    <router-view :contactInfo="contactInfo"/>
    <Footer
    :contactInfo="contactInfo"
    />
  </div>
</main>
</template>

<script>
import Nav from './components/Nav.vue';
import Footer from './components/Footer.vue';
export default {
  name: "App",
  components: {
    Nav,
    Footer
  },
  data() {
        return{
            contactInfo: [
                {
                    'method': 'Email',
                    'contact': 'grojaspiano@gmail.com'
                },
                {
                    'method': 'Phone',
                    'contact': '262-909-5892'
                },
                {
                    'method': 'Location',
                    'contact': 'Kenosha, WI'
                }
            ]
        }
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
  .app{
    display:flex;
    flex-direction: column;
    position: relative;
    min-height: 100vh;
    /* margin-bottom: 30vh; */
    padding-bottom: 20rem;
  }
  @media (max-width: 800px){
    .app{
      padding-bottom: 40rem;
    }
  }
</style>
