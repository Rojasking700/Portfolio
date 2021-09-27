<template>
    <div class="project-card">
        <div class="project-left">
            <Carousel class="carousel" v-slot="{ currentSlide }" :project="project"> 
                <Slide v-for="(slide, index) in project.imgs" :key="index" :project="project">
                    <div v-show="currentSlide === index + 1" class="slide-info">
                    <img :src="slide" alt="" />
                    </div>
                </Slide>
            </Carousel>
        </div>
        <div class="project-right">
           <h1>{{ project.title }}</h1> 
           <h2>{{ project.sub }}</h2>
           <br>
           <h3>Summary:</h3>
           <p>{{ project.brief }}</p>
           <br>
           <h3>Problems I overcame:</h3>
           <p>{{ project.problems}}</p>
           <br>
           <!-- <h3>Skills used:</h3> -->
            <ul class="project-skill-list">
                <li v-for="skill in project.skills" :key="skill" >{{ skill.title }}</li>
            </ul>
            <div class="effect thurio" id="project-effect">
                <a :href="project.gitLink" class="github" title="View Github source code"><i class="fa fa-github" aria-hidden="true"></i></a>
            </div>
           <!-- </div> -->
        </div>
    </div>
    
</template>

<script>
import Carousel from './Carousel.vue'
import Slide from './Slide.vue'
export default {
  components: { Carousel, Slide },
    names: 'project',
    props: ['project']
}
</script>

<style>
    .project-card{
        position: relative;
        width:80%;
        display: flex;
        justify-content: space-around;
        flex-direction: row;
        transition: 0.4s ease-out;
        /* background-image: linear-gradient(160deg, #00a2ff 0%, #8efff2 55%); */
        /* box-shadow:  0 0px 12px 0 rgba(0,0,0,0.4); */
        border-radius: 10px;
        margin: 20px 0;
        background: #FFFFFF;
        
        box-shadow:  0 4px 8px 0 rgba(0,0,0,0.2);
    }
    .project-right{
        width: 50%;
        margin-left: 10px;
        border-radius: 10px;
        background: rgba(255,255,255,0.);
        overflow: none;
        padding: 10px 10px;
    }
    .project-card h1{
        font-size: 3rem; 
        font-weight: 100;
    }
    .project-card h2{
        font-weight: 100;
    }
    .project-card h3{
        font-weight: 100;
    }
    .project-bottom{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .project-skill-list{
        color:black;
        display:flex;
        flex-direction:row;
    }
    .project-skill-list {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        margin-right: 60px 
    }
    .project-skill-list li{
        padding: 10px;
        margin: 0 7.5px 7.5px 0;
        box-shadow:  0 2px 4px 0 rgba(0,0,0,0.2);
        border: 1px solid rgba(0, 0, 0, 0.123);
        /* background: #2cfae9; */
        border-radius: 10px;
        font-family: 'Montserrat', sans-serif;
        transition: 0.25s ease-out;
        display: flex;
        align-items: center;
        
    }
    /* .project-skill-list li:hover{
        transition: 0.25s ease-out;
        box-shadow:  0 4px 8px 0 rgba(0,0,0,0.8);
        transform: scale(1.09);
        font-weight: 900;
    } */
    #project-effect{
        position: absolute;
        right:10px;
        bottom: 10px;
    }
    #projects-effect a {
        color: rgb(255, 255, 255);
        border: 2px solid rgb(255, 255, 255);
    }
    .project-left{
        width: 700px;
        /* max-width: 400px; */
        display: flex;
        justify-content: center;
        align-items: center;
        /* background: rgba(0, 0, 0, 0.04); */
        border-radius:10px;
    }
    /* .project-img{
        
        border: 1px solid rgba(0, 0, 0, 0.123);
        width: 95%;
        border-radius:10px;
        transition: 0.25s ease-out;
    } */

    .carousel{
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        max-width: 100%;
        /* max-height: 100%; */
        /* height: 100%; */
    }

    .slide-info{
        /* position: absolute; */
        display: flex;
        justify-content: center;
        align-items: center;
        /* top:0; */
        /* left:0; */
        width: 100%;
        /* max-height: 100%; */
        /* height: 100%; */
    }
    .carousel img{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        border-radius:10px;
        /* min-width: 100%; */
        /* height: 100%; */
        /* object-fit: cover; */
    }
   
    /* @media (min-width: 1200px){
        .project-img:hover{
            transform: scale(1.25);
            transition: 0.25s ease-out;
        }
    } */

    @media (max-width: 1200px){
        .project-card{
            flex-direction: column;
            width:90%;
            transition: 0.5s ease-out;
        }
        .project-left{
            width: 100%;
        }
        .project-right{
            width: 100%;
            padding: 0 10px;
            margin: 0;
        }
        .project-img{
            margin: 2% 0;
        }
    @media (max-width: 800px) {
        
    }
    }
</style>