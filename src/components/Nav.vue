<template>
    <nav class="nav">
        <h1 id="logo">
            <img src="../assets/crown.png" >
             Rojasking
             </h1>
        <ul class="nav-links">
            <li>Home</li>
            <li>Contact</li>
            <li>About</li>
        </ul>   
    </nav>
</template>

<style>
    .nav {
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
    nav img {
        height:2vw;
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

</style>