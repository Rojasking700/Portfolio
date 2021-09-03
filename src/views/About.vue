<template>
<main>
    <section class="about-landing">
        <div class="about-big-text">
          <div class="experience">
            <div class="about-bitext">
              <h1 >About</h1>
              <h2>I want to make a difference in the world!</h2>
              <p>I want to help small businesses like yours grow and revolutionize the world. 
                I too have big dreams of innovating the world we live in. Through web development I can help spread 
                your message and flourish your business to get it where you want to be.</p>
            </div>
            <div class="about-bitext">
              <h1>Experience</h1>
              <h2>How I got to where I am today</h2>
              <p>I have been coding for a few years now but my most professional experience comes from Coding Temple. 
                This is where I learned Full-stack web development and data science. You can learn more about these skills on my home page. 
                Before Coding Temple I attended Gateway Technical college where I learned C# and .net. Prior to that I was mostly self 
                taught learning how to code on a raspberry pi making IOT projects in python. I have also worked in the manufacturing 
                industry where I was a maintenance mechanic. Here I diagnosed mechanical, electrical, and software issues on industrial machines.</p>
            </div>
          </div>
          <div class="experience">
              <div class="about-bitext">
                <h1 >A right</h1>
                <h2>I want to make a difference in the world!</h2>
                <p>I want to help small businesses like yours grow and revolutionize the world. 
                  I too have big dreams of innovating the world we live in. Through web development I can help spread 
                  your message and flourish your business to get it where you want to be.</p>
              </div>
              <div class="about-bitext">
                <h1>E Right</h1>
                <h2>I want to make a difference in the world!</h2>
                <p>I want to help small businesses like yours grow and revolutionize the world. 
                  I too have big dreams of innovating the world we live in. Through web development I can help spread 
                  your message and flourish your business to get it where you want to be.</p>
              </div>
            </div>
          </div>
    </section>
</main>
    <div class="intro">
        <div class="intro-text">
            <h1 class="hide">
                <span class="text">Dream</span>
            </h1>
            <h1 class="hide">
                <span class="text">Create</span>
            </h1>
            <h1 class="hide">
                <span class="text">Inovate</span>    
            </h1>
        </div>
    </div>

</template>

<script>
// import {ref} from 'vue'
import gsap from 'gsap'

export default {
    mounted() {
        const tl = gsap.timeline({defaults: {ease: 'power1.out'} })

        tl.to('.text', {y:'0%', duration:1 , stagger: 0.25})
        tl.to('.intro', {y:"-120%", duration: 1})
        tl.fromTo('nav', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.about-big-text', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.footer', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')


    }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Fjalla+One&display=swap');
    /*src\assets\tudor-baciu-vc3iVL_znJ8-unsplash.jpg  */

    .about-landing{
        position: relative;
        background: url('../assets/tudor-baciu-vc3iVL_znJ8-unsplash.jpg');
        background-size: cover;
        background-position: center center;
        display: flex;
        justify-content: center;
        min-height: 1000px;
        height: 100vh;
        }
    .about-big-text{
        /* margin: 3%; */
        padding: 5%;
        font-family: 'Fjalla One', sans-serif;
        position: absolute;
        font-size: 4vw;
        color: rgb(255, 255, 255);
        text-shadow:4px 6px 8px rgb(0, 0, 0);
        text-align: center;
        background: rgba(0,0,0,0.25);
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .experience{
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
      width: 40%;
    }
    .about-bitext{
      padding: 0.5rem;
      /* width:80%; */
      /* transform: translate( -5%,5%); */
      display:flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    .about-big-text h1 {
      font-size: 4rem;
      width:90%;
    }
    .about-big-text h2 {
      font-size: 2rem;
      width:90%;
    }
    .about-bitext p{
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        font-family: 'Montserrat', sans-serif;
        font-weight: 900;
        font-size: 1.25rem;
        /* width: 40%; */
        /* transform: translate( 0%, 0%); */
        text-shadow:3px 3px 2px rgb(0, 0, 0);
    }
    @media (max-width: 800px){
        .about-big-text {
          font-size: 12vw;
          width: 100%;
        }
        .about-bitext{
          top:10%;
          left:40%;
          width:80%;
        }
      .about-bitext h1 {
        font-size: 12vw;
      }
      .about-bitext h2 {
        font-size: 5vw;
      }
        .about-bitext p {
            width: 100%;
            font-size: 4vw;
            transform: translate(0,0);
            text-shadow:2px 2px 1px rgb(0, 0, 0);
        }

    }
    .intro{
        background: black;
        position: fixed;
        top:0;
        left: 0;
        width: 100%;
        height: 100%;
        display:flex;
        justify-content: center;
        align-items: center;
    }
    .intro-text{
        padding: 80px;
        color: #fff;
        font-size: 3rem;
        text-align: center;
    }
    .text{
        padding: 20px;
    }
    .hide{
        background: black;
        overflow: hidden;
    }
    .hide span{
        transform: translateY(100%);
        display: inline-block;
    }
</style>