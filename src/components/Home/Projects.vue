<template>
    <div class="project-card">
        <div class="project-left">
            <img class="project-img" :src="project.imgs[0]" alt="">
        </div>
        <div class="project-right">
           <h1>{{ project.title }}</h1> 
           <h2>{{ project.sub }}</h2>
           <p>{{ project.brief }}</p>
           <br>
           <h3>Skills Used:</h3>
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
export default {
    names: 'project',
    props: ['project']
}
</script>

<style>
    .project-card{
        position: relative;
        width:70%;
        display: flex;
        justify-content: space-around;
        flex-direction: row;
        border: 1px solid black;
        padding: 5px;
        margin: 5px 0;
    }
    .project-right{
        width: 60%;
        margin-left: 20px;
        border: 1px solid black;
        overflow: none;
    }
    .project-card h1{
        font-size: 3rem;
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
        margin: 5px;
        box-shadow:  0 2px 4px 0 rgba(0,0,0,0.2);
        border: 1px solid rgba(0, 0, 0, 0.123);
        border-radius: 10px;
        transition: 0.25s ease-out;
        display: flex;
        align-items: center;
    }
    .project-skill-list li:hover{
        transition: 0.25s ease-out;
        box-shadow:  0 4px 8px 0 rgba(0,0,0,0.8);
        transform: scale(1.09);
    }
    #project-effect{
        position: absolute;
        right:10px;
        bottom: 10px;
    }
    .project-left{
        width: 40%;
        border: 1px solid black;
    }
    .project-img{
        width: 300px;
        border: 1px solid black;
    }
</style>