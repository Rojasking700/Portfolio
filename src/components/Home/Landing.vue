<template>
<main>
    <section class="landing">
        <div class="big-text">
        <h1 class="bitext">Gabriel Rojas</h1>
        <p class="intro-par">"Design is a funny word. Some people think design means how it looks. But of course, if you dig deeper, it's really how it works"</p> 
        <p class="intro-par">-Steve Jobs </p>
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

        tl.to('.text', {y:'0%', duration:.75 , stagger: 0.25})
        tl.to('.intro', {y:"-140%", duration: 1})
        tl.fromTo('nav', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.big-text', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.skills-header', {opacity:0}, {opacity: 0.75, duration: 0.75},'=-0.75')
        tl.fromTo('.skills', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.projects', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.footer', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')


    }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Fjalla+One&display=swap');

    .landing{
        position: relative;
        background: url('../../assets/mark-rohan-vN7Cpe2MSf8-unsplash.jpg');
        background-size: cover;
        background-position: center center;
        display: flex;
        justify-content: center;
        min-height: 1000px;
        height: 100vh;
        }
    .big-text{
        margin: 3%;
        font-family: 'Fjalla One', sans-serif;
        position: absolute;
        top:20%;
        left:20%;
        font-size: 5vw;
        color: rgb(255, 255, 255);
        text-shadow:4px 6px 8px rgb(0, 0, 0);
        text-align: center;
        transform: translate( -50%,-25%);
    }
    .intro-par{
        font-family: 'Fjalla One', sans-serif;
        display: flex;
        justify-content: center;
        font-size: 2vw;
        width: 50%;
        transform: translate( 50%, 0%);
        text-shadow:3px 3px 4px rgb(0, 0, 0);
    }
    @media (max-width: 800px){
        .big-text {
            top:10%;
            left:45%;
            transform: translate( -50%,-20%);
            font-size: 12vw;
            width: 80%;
        }
        .intro-par{
            width: 100%;
            font-size: 5vw;
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