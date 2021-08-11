<template>
<main>
    <section class="landing">
        <h1 class="big-text">Gabriel Rojas</h1>
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
        tl.to('.intro', {y:"-100%", duration: 1})
        tl.fromTo('nav', {opacity:0}, {opacity: 1, duration: 1})
        tl.fromTo('.big-text', {opacity:0}, {opacity: 1, duration: 1},'=-0.5')
    }
}
</script>

<style>

    .landing{
        background: url('../assets/wei-zeng-6KffRaLsClk-unsplash.jpg');
        background-size: cover;
        display: flex;
        justify-content: center;
        min-height: 100vh;
        /* height: 100%;
        width: 100%; */
    }
    
    .big-text{
        position: absolute;
        top:20%;
        left:25%;
        transform: translate( -50%,-30%);
        font-size:5rem;
        color: #fff;
        text-shadow: 4px 4px black;
    }
    @media (max-width: 800){
        .big-text {
            top:30%;
            left:50%;
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
        background: url('../assets/red_animated_S15.png');
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
        color: #fff;
        font-size: 3rem;
        text-align: center;
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