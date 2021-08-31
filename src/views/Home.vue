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
          title: 'Python',
          Category:'Language',
          bgtext: 'Python',
          src: require('../assets/Skills/Python-Logo.png'),
          detail: 'Python is an interpreted, object-oriented, high-level programming language. I have utilized Python and its many libraries to manipulate, anaylze, and extract data.'
        },
        {
          title: 'Javascript',
          Category:'Language',
          bgtext: 'JS',
          src: require('../assets/Skills/Javascript-Logo.png'),
          detail: 'JavaScript is a lightweight, interpreted, object-oriented language. Most of the logic and animations from this website were created with JavaScript.'
        },
        {
          title: 'Structured Query Language',
          Category:'Language',
          bgtext: 'SQL',
          src: require('../assets/Skills/SQL-Logo.png'),
          detail: 'SQL is a relational query language that is used for accessing, storing, and manipulating data in a relational database.'
        },
        {
          title: 'HTML-5',
          Category:'Language',
          bgtext: 'HTML5',
          src: require('../assets/Skills/HTML5-Logo.png'),
          detail: 'HTML is the backbone of web development. It is the official web standard. This is the most basic and fundamental skill of web developers.'
        },
        {
          title: 'CSS',
          Category:'Language',
          bgtext: 'CSS',
          src: require('../assets/Skills/CSS-Logo.png'),
          detail: 'CSS is another vital part of web development. It provides amazing UX/UI capabilities. Without the styling of CSS this site and many others would be plain and boring.'
        },
        {
          title: 'C#',
          Category:'Language',
          bgtext: 'C#',
          src: require('../assets/Skills/C-Sharp-Logo.png'),
          detail: 'C# is a multi-paradigm language that enables a variety of secure and robust applications that runs on the .NET framework.'
        },
        {
          title: 'React.js',
          Category:'Framework',
          bgtext: 'React',
          src: require('../assets/Skills/React-Logo.png'),
          detail: 'React is a front-end JavaScript library for building UX/UI components. I have created front-end applications with the ability to create, retrieve, update, and delete data.'
        },
        {
          title: 'Flask',
          Category:'Framework',
          bgtext: 'FLASK',
          src: require('../assets/Skills/Flask-Logo.png'),
          detail: 'Flask is a micro web framework written in python. Using Flask I developed a backend/API to transmit data from the SQL database and translated the data to JSON with Flask.'
        },
        {
          title: 'Vue.js',
          Category:'Framework',
          bgtext: 'VUE',
          src: require('../assets/Skills/Vue-Logo.png'),
          detail: 'Vue is an open source progressive JavaScript framework used to develop interactive web interfaces. In fact I made this website using Vue!'
        },
        {
          title: 'Raspberry Pi',
          Category:'Technology',
          bgtext: 'RaspPi',
          src: require('../assets/Skills/Raspberry-pi-Logo.png'),
          detail: 'Raspberry Pi is a credit-card sized computer that is capable of doing everything you’d expect from a desktop computer. I taught myself the fundamentals of python and electronics using this board.'
        },
        {
          title: 'Arduino',
          Category:'Technology',
          bgtext: 'Arduino',
          src: require('../assets/Skills/Arduino-Logo.png'),
          detail: 'Arduino is a microcontroller board. Along with the raspberry pi i have created various electronic and iot projects. The combination of hardware and software make the learning experience fun.'
        },
        {
          title: 'Programmable logic controllers',
          Category:'Technology',
          bgtext: 'PLC',
          src: require('../assets/Skills/Allen-Bradley-Logo.png'),
          detail: 'A PLC is an industrial computer control system that continuously monitors the state of input devices and makes decisions based upon a custom program to control the state of output devices.'
        },
        {
          title: 'Google',
          Category:'Resource',
          bgtext: 'GOOGLE',
          src: require('../assets/Skills/Google-Logo.png'),
          detail: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maxime aliquid debitis vero ab veniam. Magnam amet ea laboriosam eius quibusdam?'
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
  padding-top: 10px
}
 @media (max-width: 800px) {
   .skills{
     max-width: 80%;
   }
 }

</style>