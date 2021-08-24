<template>
  <section  @mousemove="mousemove">
    <div class="home">
      <Landing class="Landing"/>
      <Iam class="Iam"/>

      <h1 class="skills-header">Languages:</h1>
      <section class="skills" >
          <Skills  
            v-for="skill in skills" v-show="skill.Category==='Language'"
            :key=skill.title
            :skill="skill"
          />
      </section>

      <h1 class="skills-header">Frameworks:</h1>
      <section class="skills" >
          <Skills  
            v-for="skill in skills" v-show="skill.Category==='Framework'"
            :key=skill.title
            :skill="skill"
          />
      </section> 

      <h1 class="skills-header">Technologies:</h1>
      <section class="skills" >
          <Skills  
            v-for="skill in skills" v-show="skill.Category==='Technology'"
            :key=skill.title
            :skill="skill"
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
          title: 'Raspberry Pi',
          Category:'Technology',
          bgtext: 'RaspPi',
          src: require('../assets/Skills/Raspberry-pi-Logo.png'),
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
          title: 'Allen-Bradley',
          Category:'Technology',
          bgtext: 'PLC',
          src: require('../assets/Skills/Allen-Bradley-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'Python',
          Category:'Language',
          bgtext: 'Python',
          src: require('../assets/Skills/Python-Logo.png'),
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
          title: 'SQL',
          Category:'Language',
          bgtext: 'SQL',
          src: require('../assets/Skills/SQL-Logo.png'),
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
          title: 'React.js',
          Category:'Framework',
          bgtext: 'React',
          src: require('../assets/Skills/React-Logo.png'),
          detail: 'stuff'
        },
        
        {
          title: 'Vue.js',
          Category:'Framework',
          bgtext: 'VUE',
          src: require('../assets/Skills/Vue-Logo.png'),
          detail: 'stuff'
        },
        {
          title: 'C#',
          Category:'Language',
          bgtext: 'C#',
          src: require('../assets/Skills/C-Sharp-Logo.png'),
          detail: 'stuff'
        },
      ]
    }
  },
}
</script>

<style>
.skills{
  display:flex;
  /* flex-wrap: wrap; */
  justify-content: space-between;
  top:0;
  left:0;
  max-width: 70%;
  padding: 25px 0;
  margin: auto;
  overflow-x: auto;
  /* align-items: center; */
}

.skills-header {
  display: flex;
  justify-content: center;
  font-size: 3vw;
}


</style>