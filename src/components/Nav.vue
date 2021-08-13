<template>
    <header :class="{ 'scrolled-nav' : scrolledNav }">
        <nav>
            <div class="branding">
                    <router-link class="branding" :to="{name: 'Home'}">
                        <img src="../assets/crown1.png" alt="">
                        <h4>Rojasking700</h4>
                    </router-link>
            </div>
            <ul v-show="!mobile" class="navigation">
                <li><router-link class="link" :to="{name: 'Home'}">Home</router-link></li>
                <li><router-link class="link" :to="{name: 'About'}">About</router-link></li>
                <li><router-link class="link" :to="{name: ''}">Portfolio</router-link></li>
                <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
            </ul>
            <div class="icon">
                <i @click="toggleMobileNav" v-show="mobile" class="far fa-bars" :class="{'icon-active' : mobileNav}"></i>
            </div>
            <transition name="mobile-nav">
                <ul v-show="mobileNav" class="dropdown-nav">
                    <div class="list">
                        <li><router-link class="link" :to="{name: 'Home'}">Home</router-link></li>
                        <li><router-link class="link" :to="{name: ''}">About</router-link></li>
                        <li><router-link class="link" :to="{name: ''}">Portfolio</router-link></li>
                        <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
                    </div>
                </ul>
            </transition>
        </nav>
    </header>
</template>

<script>
export default {
    name: "Nav",
    data() {
        return {
            scrolledNav: null,
            mobile: null,
            mobileNav: null,
            windowWidth: null
        }
    },
    created() {
        window.addEventListener('resize', this.checkScreen);
        this.checkScreen();
    },
    methods : {
        toggleMobileNav () {
            this.mobileNav = !this.mobileNav;
        },

        updateScroll() {
            const scrollPosition = window.scrollY;
            if (scrollPosition > 50) {
                this.scrolledNav = true;
                return;
            }
            this.scrolledNav = false;
        },

        checkScreen() {
            this.windowWidth = window.innerWidth;
            if(this.windowWidth <= 800){
                this.mobile = true;
                return;
            }
            this.mobile = false;
            this.mobileNav = false;
            return;
        }
    },
};
</script>

<style>

    header { 
        /* background-color: rgba(0,0,0,0.8); */
        z-index: 99;
        width: 100%;
        position: fixed;
        transition: .5s ease all;
        color: #fff;
        text-shadow: 2px 2px black;
    }

    nav {
        position: relative;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 10px;
        transition: .5s ease all;
        width: 100%;
        font-size: 2vw;
        margin: 0 auto;
    }
    

    ul, .link{
        font-weight: 500;
        color: #fff;
        list-style: none;
        text-decoration: none;
    }

    li{
        text-transform: uppercase;
        padding: 16px;
        margin-left: 16px;
    }

    .link {
        font-size: 1vw;
        transition: .5s ease all;
        padding-bottom: 4px;
        border-bottom: 1px solid transparent;
    }
    .link:hover{
        color: #00afea;
        border-color: #00afea;
    }

    .branding{
        color: #fff;
        display: flex;
        align-items: center;
        flex-direction: row;
        width: 100%;
        font-size: 2vw;
        text-decoration: none;
    }

    .branding img {
        /* position: absolute; */
        width: 4.5vw;
        transform: rotate(-30deg);
        transition: .5s ease all;
    }
    @media (max-width: 800px) {
        .branding{
            font-size: 4vw;
        }
        .branding img {
            width: 6vw;
        }
        
    }
    
    .navigation{
        display: flex;
        align-items: center;
        flex: 1;
        justify-content: flex-end;
    }

    .icon {
        display: flex;
        align-items: center;
        position: absolute;
        top: 0;
        right: 24px;
        height: 100%;
        z-index: 101;
    }

    .icon i {
        cursor: pointer;
        font-size: 24px;
        transition: .8s ease all;
    }

    .icon-active {
        transform: rotate(90deg);
        color:black;
        text-shadow: 2px 2px rgba(0, 0, 0, 0.212);
    }
    .dropdown-nav {
        display: flex;
        flex-direction: column;
        position: fixed;
        width: 100%;
        max-width: 33vw;
        min-width: 150px;
        height: 100%;
        background-color: #fff;
        top:0;
        right:0;
    }

    .dropdown-nav .list{
        display: flex;
        align-items: flex-end;
        flex-direction: column;
        position: absolute;
        top: 30%;
        right: 0;
        padding: 5px;
    }
    .dropdown-nav li {
        margin-left: 0;
    }
    .dropdown-nav li .link {
        color: #000;
        font-size: 4vw;
        text-shadow: none;
    }

     .mobile-nav-enter-active,
     .mobile-nav-leave-active {
        transition: 1s ease all;

    }

     .mobile-nav-enter-from,
     .mobile-nav-leave-to{
        transform: translateX(250px);
    }

     .mobile-nav-enter-to {
        transform: translateX(0);
    }

</style>

