<template>
  <section  @mousemove="mousemove">
    <div class="home">
      <Landing class="Landing"/>
      <Iam class="Iam"/>

      <section class="skills">
        <Skills  
          v-for="skill in skills"
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

// import { ref, onMounted, onUnmounted } from "vue";

export default {
  name: 'Home',
  components: {
    Landing,
    Iam,
    Skills
  },
  
  data() {
    return{
      // x:0,
      // y:0,
      // viewportHeight: 1,
      // viewportWidth: 1,
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
  },
  // created () {
  //     this.updateViewportSize()
  //   },

  //   mounted () {
  //     document.addEventListener('mousemove', this.onMouseMove)
  //     window.addEventListener('resize', this.updateViewportSize)
  //   },

  //   unmounted () {
  //     document.removeEventListener('mousemove', this.onMouseMove)
  //     window.removeEventListener('resize', this.updateViewportSize)
  //   },

  //   computed: {
  //     SkillStyle () {
  //         console.log(this.x,this.y)
  //       return {
  //         left: percent(this.x, this.viewportWidth),
  //         top: percent(this.y, this.viewportHeight)
  //       }

  //       function percent (value, total) {
  //           return Math.round((value * 100 / total)) + '%'
  //       }
  //     },
  //       styles2 () {
  //           return {
  //           right: percent(this.x, this.viewportWidth),
  //           bottom: percent(this.y, this.viewportHeight)
  //           }
  //           function percent (value, total) {
  //               return Math.round((value * 100 / total)) + '%'
  //           }
  //       }
  //   },

  //   methods: {
  //     onMouseMove (ev) {
  //       this.x = ev.clientX
  //       this.y = ev.clientY
  //     },

  //     updateViewportSize () {
  //       this.viewportHeight = window.innerHeight
  //       this.viewportWidth = window.innerWidth
  //     }
  //   }
  // mousemove(e) {
  //   const { x, y } = this.useMouse();

  //   let mouseX = x;
  //   let mouseY = y;

  //   console.log('hello',x ,y, e);

  //   let skills = document.querySelectorAll('.skills .skill');

  //   for (let i=0; i<skills.length; i++) {
  //     let skill = skills[i];

  //     let skill_image = skill.querySelector('.skill-image-wrap');

  //     let img_x = mouseX - this.coords(skill_image).x;
  //     let img_y = mouseY - this.coords(skill_image).y;
  //     skill_image.style.transform = `translateY(-${img_y/20}px) translateX(-${img_x/20}px) translateZ(100px)`;

  //     let bgtext = skill.querySelector('.bg-text');
  //     let bg_x = mouseX - this.coords(bgtext).x;
  //     let bg_y = mouseY = this.coords(bgtext).y;

  //     bgtext.style.transform = `translateX(${bg_x/25}px) translateY(${bg_y/25}px)`;
  //   }
  // },
  // coords(el){
  //   let coords = el.getBoundingClientRect();
    
  //   return {
  //     x: coords.left / 2,
  //     y: coords.top / 2 
  //   }
  // }
    
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