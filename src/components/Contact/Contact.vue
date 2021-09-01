<template>
<main class="contact-main">
    <section class="contact-landing">
        <div class="contact-big-text">
        <h1 class="contact-bitext">Contact me</h1>
        <!-- <p class="contact-intro-par">"Design is a funny word. Some people think design means how it looks. But of course, if you dig deeper, it's really how it works" -Steve Jobs</p> -->
        </div>
    </section>
</main>
    <div class="contact-intro">
        <div class="contact-intro-text">
            <h1 class="contact-hide">
                <span class="contact-text">Dream</span>
            </h1>
            <h1 class="contact-hide">
                <span class="contact-text">Create</span>
            </h1>
            <h1 class="contact-hide">
                <span class="contact-text">Inovate</span>    
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
        const C1 = gsap.timeline({defaults: {ease: 'power1.out'} })

        C1.to('.contact-text', {y:'0%', duration:1 , stagger: 0.25})
        C1.to('.contact-intro', {y:"-120%", duration: 1})
        C1.fromTo('nav', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        C1.fromTo('.contact-big-text', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        C1.fromTo('.footer', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')


    }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Fjalla+One&display=swap');
    /* src\assets\pavan-trikutam-71CjSSB83Wo-unsplash.jpg */
    .contact-landing{
        position: relative;
        background: url('../../assets/pavan-trikutam-71CjSSB83Wo-unsplash.jpg');
        background-size: cover;
        background-position: center center;
        display: flex;
        justify-content: center;
        min-height: 100vh;
        height: 100vh;
        }
    .contact-big-text{
        margin: 3%;
        font-family: 'Fjalla One', sans-serif;
        position: absolute;
        top:10%;
        left:45%;
        font-size: 4rem;
        color: rgb(255, 255, 255);
        text-shadow:4px 6px 8px rgb(0, 0, 0);
        text-align: center;
        transform: translate( -45%,-25%);
    }
    .contact-intro-par{
        display: flex;
        justify-content: center;
        font-size: 1vw;
        width: 50%;
        transform: translate( 45%, 0%);
    }
    @media (max-width: 800px){
        .contact-big-text {
            top:15%;
            left:50%;
            font-size: 12vw;
            width: 80%;
            transform: translate( -50%,-25%);
        }
        .contact-intro-par{
            width: 100%;
            font-size: 5vw;
            transform: translate(0,0);
        }

    }
    .contact-intro{
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
    .contact-slider {
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
    .contact-intro-text{
        padding: 80px;
        color: #fff;
        font-size: 3rem;
        text-align: center;
    }
    .contact-text{
        padding: 20px;
    }
    .contact-hide{
        background: black;
        overflow: hidden;
    }
    .contact-hide span{
        /* padding: 1; */
        transform: translateY(100%);
        display: inline-block;
    }
</style>