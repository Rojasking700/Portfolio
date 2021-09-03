
<template>
<main class="contact-main">
    <section class="contact-landing">
        <div class="contact-big-text">
        <h1 class="contact-bitext">Contact me</h1>
        <p class="contact-intro-par">Please contact me if you have any questions about me or my experience, any questions regarding how this site was made, any suggestions you may have to make the site better or if you find any bugs that need fixing. I am available at any time for a phone call or email. I would love to get in touch with you and learn more about you or your company as well!</p>
        </div>
        <div class="contactcards">
        <ContactCards 
        v-for="contact in contactInfo"
        :key=contact.method
        :contact=contact
        />
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

import ContactCards from '../components/Contact/ContactCards.vue'
import gsap from 'gsap'

export default {
    name: 'contactInfo',
    props:['contactInfo'],
    components: {
        ContactCards
    },
    mounted() {
        const C1 = gsap.timeline({defaults: {ease: 'power1.out'} })

        C1.to('.contact-text', {y:'0%', duration:1 , stagger: 0.25})
        C1.to('.contact-intro', {y:"-140%", duration: 1})
        C1.fromTo('nav', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        C1.fromTo('.contact-big-text', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')
        C1.fromTo('.footer', {opacity:0}, {opacity: 1, duration: 0.75},'=-0.75')


    }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Fjalla+One&display=swap');
    .contact-main{
        display:flex;
        flex-direction: column;

    }
    .contact-landing{
        position: relative;
        background: url('../assets/pavan-trikutam-71CjSSB83Wo-unsplash.jpg');
        background-size: cover;
        background-position: center center;
        display: flex;
        justify-content: center;
        min-height: 1000px;
        height: 100vh;
    }
    .contact-big-text{
        font-family: 'Fjalla One', sans-serif;
        position: absolute;
        top:30%;
        left:50%;
        font-size: 4vw;
        color: rgb(255, 255, 255);
        text-shadow:4px 6px 8px rgb(0, 0, 0);
        text-align: center;
        transform: translate( -50%,-20%);
        background: rgba(0,0,0,0.25);
        width: 100%;
        height: 100%;
    }
    .contact-intro-par{
        display: flex;
        justify-content: center;
        font-size: 1.5rem;
        width: 70%;
        transform: translate( 20%, 0%);
        text-shadow:2px 4px 4px rgb(0, 0, 0);
    }
    @media (max-width: 800px){
        .contact-big-text {
            margin: 0;
            padding: 10% 5%;
            top:25%;
            left:50%;
            font-size: 12vw;
            transform: translate( -50%,-25%);
        }
        .contact-intro-par{
            width: 100%;
            font-size: 1.2rem;
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
        position: absolute;
        background-size: cover;
        display: flex;
        justify-content: center;
        top: 0;
        right: 0  ;
        width: 100%;
        height: 100%;
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
        transform: translateY(100%);
        display: inline-block;
    }
    .contactcards{
        position: absolute;
        width: 80%;
        height: 50%;
        display:flex;
        justify-content: space-between;
        align-items: center;
        flex-wrap: wrap;
        top:50%;
    }
    @media (max-width: 1220px){
        .contactcards{
            flex-direction: column;
            justify-content: none;
            top:40%;
        }
    }
    
</style>