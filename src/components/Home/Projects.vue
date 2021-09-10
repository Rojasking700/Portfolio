<template>
    <div class="project-card">
        <div class="project-left">
            <img class="project-img" :src="project.imgs[0]" alt="">
        </div>
        <div class="project-right">
           <h1>{{ project.title }}</h1> 
           <h2>{{ project.sub }}</h2>
           <p>{{ project.brief }}</p>
           <div class="effect thurio" id="project-effect">
           <a href="https://github.com/Rojasking700" class="github" title="Join us on Github"><i class="fa fa-github" aria-hidden="true"></i></a>
           </div>
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
    .project-left{
        width: 40%;
        border: 1px solid black;
    }
    .project-img{
        width: 300px;
        border: 1px solid black;
    }
</style>