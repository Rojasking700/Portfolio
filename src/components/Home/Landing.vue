<template>
<main>
    <section class="landing">
        <div class="big-text">
        <h1 class="bitext">Gabriel Rojas</h1>
        <p class="intro-par">"Design is a funny word. Some people think design means how it looks. But of course, if you dig deeper, it's really how it works" -Steve Jobs</p>
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

    <!-- <div class="slider"></div> -->
</template>

<script>
// import {ref} from 'vue'
import gsap from 'gsap'

export default {
    mounted() {
        const tl = gsap.timeline({defaults: {ease: 'power1.out'} })

        tl.to('.text', {y:'0%', duration:1 , stagger: 0.25})
        // tl.fromTo('.slider', {y:"-50%", x:"50%", width:"0%", height:"0%", }, {y:"50%",x:"-100%", width:"100vw", height:"100vh",  duration: 10, delay: 0.5})
        tl.to('.intro', {y:"-120%", duration: 1})
        tl.fromTo('nav', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.big-text', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.skills', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        tl.fromTo('.skills-header', {opacity:0}, {opacity: 0.75, duration: 0.75},'=-0.75')
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
        min-height: 100vh;
        height: 100vh;
        }
    .big-text{
        margin: 3%;
        font-family: 'Fjalla One', sans-serif;
        position: absolute;
        top:20%;
        left:25%;
        font-size: 5vw;
        color: rgb(255, 255, 255);
        text-shadow: 3px 3px 4px rgb(0, 0, 0);
        text-align: center;
        transform: translate( -50%,-25%);
    }
    .intro-par{
        display: flex;
        justify-content: center;
        font-size: 2vw;
        width: 50%;
        transform: translate( 45%, 0%);
    }
    @media (max-width: 800px){
        .big-text {
            top:30%;
            left:50%;
            font-size: 15vw;
        }
        .intro-par{
            width: 100%;
            font-size: 5vw;
            transform: translate(0,0);
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
    .slider {
        /* margin:50%; */
        /* padding: 10%; */
        position: absolute;
        /* background: url('../../assets/red_animated_S15.png'); */
        background-size: cover;
        display: flex;
        justify-content: center;
        /* position: fixed; */
        top: 0;
        right: 0  ;
        width: 100%;
        height: 100%;
        /* transform: translateY(100%);
        transform: translateX(100%); */
        overflow: visible;
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
        /* padding: 1; */
        transform: translateY(100%);
        display: inline-block;
    }
</style>