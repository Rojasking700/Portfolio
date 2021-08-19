<template>
  <section>
    <div class="home">
      <Landing class="Landing"/>
      <Iam class="Iam"/>

      <section class="skills">
        <Skills  
          v-for="skill in skills"
          :key=skill.title
          :skill="skill"
          :v-if="skill.Category === 'Technology'"
        />
      </section>

    </div>

  </section>
</template>

<script>
// import gsap from 'gsap'
import Iam from '../components/Home/Iam.vue';
import Landing from '../components/Home/Landing.vue';
import Skills from '../components/Home/Skills.vue';

export default {
  name: 'Home',
  components: {
    Landing,
    Iam,
    Skills
  },
  data() {
    return{
      skills: [
        {
          title: 'Allen-Bradley',
          Category:'Technology',
          bgtext: 'PLC',
          src: require('../assets/Skills/Allen-Bradley-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'Arduino',
          Category:'Technology',
          bgtext: 'Arduino',
          src: require('../assets/Skills/Arduino-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'C#',
          Category:'Language',
          bgtext: 'C#',
          src: require('../assets/Skills/C-Sharp-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'CSS',
          Category:'Language',
          bgtext: 'CSS',
          src: require('../assets/Skills/CSS-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'Flask',
          Category:'Framework',
          bgtext: 'FLASK',
          src: require('../assets/Skills/Flask-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'Google',
          Category:'Resource',
          bgtext: 'GOOGLE',
          src: require('../assets/Skills/Google-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'HTML-5',
          Category:'Language',
          bgtext: 'HTML5',
          src: require('../assets/Skills/HTML5-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'Javascript',
          Category:'Language',
          bgtext: 'JS',
          src: require('../assets/Skills/Javascript-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'Raspberry Pi',
          Category:'Technology',
          bgtext: 'RaspPi',
          src: require('../assets/Skills/Raspberry-pi-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'React.js',
          Category:'Framework',
          bgtext: 'React',
          src: require('../assets/Skills/React-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'SQL',
          Category:'Language',
          bgtext: 'SQL',
          src: require('../assets/Skills/SQL-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'Vue.js',
          Category:'Framework',
          bgtext: 'VUE',
          src: require('../assets/Skills/Vue-Logo.png'),
          detail: 'stuff'
        }
      ]
    }
  }

    
}
</script>

<style>
.skills{
  display:flex;
  flex-wrap: wrap;
  max-width: 70%;
  padding: 25px;
  margin: auto;
}


</style>