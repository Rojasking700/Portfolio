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

      <br><br><br>

      <h1 class="projects-header">Here are my projects:</h1>
      <section class="projects">
        <Projects
          v-for="project in projects"
            :key=project.title
            :project="project"
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
import Projects from '../components/Home/Projects.vue'


export default {
  name: 'Home',
  components: {
    Landing,
    Iam,
    Skills,
    Projects
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
      ],
      projects: [
        {
          title: 'Recipe_Blog',
          sub: 'Share all your favorite recipes!',
          brief: 'A blog is designed to help you share any meals you have made and any recipes you would like to share! Easily create a post or scroll through others’ posts assembled by the React frontend. All of this data is handled through the flask backend that stores and retrieves it from a database.',
          problems: 'Creating an account wasn’t as easy as it is now. When trying to create new accounts using postman, I would submit the data but it would not show up on my database. I figured out, by printing all the data coming that I was not filling all the requirements need for that model. Moral of the story: when in doubt print it out!',
          skills: [{title:'Python'},{title:'Javascript'},{title:'Flask'},{title:'React.js'},{title:'API'},{title:'SQL'},{title:'Database'},{title:'HTML'},{title:'CSS'}],
          gitLink: 'https://github.com/briannaswales/flask-react-group-2',
          imgs: [require('../assets/Projects/Recipe_blog/HomeRecipe.jpg'),require('../assets/Projects/Recipe_blog/CreatePost.jpg'),require('../assets/Projects/Recipe_blog/CreateAccountRecipe.jpg'),require('../assets/Projects/Recipe_blog/LoginRecipe.jpg')],
        },
        {
          title: 'Portfolio',
          sub:'Learn more about this website!',
          brief: 'My portfolio website was established as an online interactive resume. Here I demonstrate the skills I have learned from my own and from previous experience at coding temple. Visualized by HTML & CSS, Composed by the Vue.js framework, and animated by JavaScript!',
          problems: 'The Icons moving with the mouse proved to be a learning curve with the Vue. Previously I used vanilla Javascript that kept track of the coordinates of the mouse, but In Vue I had to create various lifecycle hooks to listen for mouse movement, update mouse coordinate, and translate the images accordingly.',
          skills: [{title:'Javascript'},{title:'Vue.js'},{title:'HTML'},{title:'CSS'},],
          gitLink: 'https://github.com/Rojasking700/Portfolio',
          imgs: [require('../assets/Projects/Portfolio/Home_Portfolio.jpg'),require('../assets/Projects/Portfolio/About_Portfolio.jpg'),require('../assets/Projects/Portfolio/Contact_Portfolio.jpg'),],
        },
        {
          title: 'MyFi',
          sub:'(My Finance) Track your stocks!',
          brief: 'MyFi is a web app designed to keep track of information and analysis. Capable of searching any stock you choose. Create your own profile and compose a custom watchlist tailored to your portfolio. Powered by a user-friendly React frontend, and transmitted the data from the Alpha Vantage API, through a Flask backend.',
          problems: 'I was unable to keep the users logged in every time they refreshed the page. Determined, I read various forums online on how to save data to local storage. With that, I was able to implement the use of tokens that expire after 60 mins.',
          skills: [{title:'Python',detail:''},{title:'Javascript'},{title:'Flask'},{title:'React.js'},{title:'API'},{title:'SQL'},{title:'Database'},{title:'HTML'},{title:'CSS'}],
          gitLink: 'https://github.com/Rojasking700/MyFi',
          imgs: [require('../assets/Projects/MyFI/FullResult.jpg'),require('../assets/Projects/MyFI/Search.jpg')],
        },
      ],
    }
  },
}
</script>

<style>
.home{
  width: 100%;
  padding-bottom: 5rem;
}
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
  /* background: rgba(0,0,0,0.04); */
  border-radius: 10px;
  /* align-items: center; */
}

.skills-header {
  display: flex;
  justify-content: center;
  color: rgb(50, 50, 50);
  font-weight: 100;
  font-size: 3vw;
  padding-top: 10px
}
.skills::-webkit-scrollbar {
	height: 5px;
}

/* Track */
.skills::-webkit-scrollbar-track {
	box-shadow: inset 0 0 5px grey;
	border-radius: 10px;
}

/* Handle */
.skills::-webkit-scrollbar-thumb {
	background: rgb(129, 190, 255);
	border-radius: 10px;
}

/* Handle on hover */
.skills::-webkit-scrollbar-thumb:hover {
	background: rgb(44, 146, 255);
}

.projects-header{
  font-size: 5rem;
  font-weight: 200;
  text-align: center;
}
.projects{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

 @media (max-width: 800px) {
   .skills{
     max-width: 80%;
   }
   .skills-header{
     font-size: 2rem;
   }
   .projects-header{
     font-size: 4rem;
   }
 }

</style>