<template>
    <header :class="{ 'scrolled-nav' : scrollPosition }">
        <div class="branding">
            <img src="../assets/crown.png" alt="">
        </div>
        <ul v-show="!mobile" class="navigation">
            <li><router-link class="link" :to="{name: 'Home'}">Home</router-link></li>
            <li><router-link class="link" :to="{name: ''}">About</router-link></li>
            <li><router-link class="link" :to="{name: ''}">Portfolio</router-link></li>
            <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
        </ul>
    </header>
</template>

<script>
export default {
    // setup() {
    //     const myFunction = () => {
    //         var x = document.getElementsById("nav");
    //         if (x.className ==="nav"){
    //             x.className += "responsive";
    //         }else {
    //             x.className = 'nav';
    //         }
    //     }

    //     return {myFunction}
    // }
}
</script>

<style>
    /* .nav {
        padding: 3rem;
        position: absolute;
        width: 100%;
        min-height: 10vh;
        z-index:1000;
        display:flex;
        align-items: center;
        justify-content: space-between;
        color: #fff;
        text-shadow: 2px 2px black;
    }
    .nav a {
        color:#fff;
        text-decoration: none;
        padding-left: 10rem;
        font-size: 1.2rem;
        display: flex;
    }
    nav img {
        height:2rem;
        transform: rotate(-30deg);

    }
    .nav-links {
        display: flex;
        list-style: none;
    }
    .nav-links li {
        padding-left: 10rem;
        font-size: 1.2rem;
    }
    .nav .icon{
        display: none;
    }

    @media (max-width: 800px) {
        .nav a { display: none;}
        .nav a.icon{
            display: block;
            float:right;
        }
    }
    @media (max-width: 800px) {
        .nav.responsive { position: relative;}
        .nav.responsive .icon {
            position: absolute;
            right: 0;
            top: 0;
        }
        .nav.responsive a{
            float: none;
            display: block;
            text-align: left;
        }
    }
     */

</style>

