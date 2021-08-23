<template>
    <div class="skill">
        <div class="skill-inner">
            <div class="skill-text-wrap">
                <h2 class="bg-text">{{ skill.bgtext }}</h2>
            </div>
            <div class="skill-image-wrap">
                <img class="image" :src="skill.src">
            </div>
            <div class="skill-detail">
                <h2>{{ skill.tittle }}</h2>
                <p>
                    <!-- {{ skill.detail }} -->
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maxime aliquid debitis vero ab veniam. Magnam amet ea laboriosam eius quibusdam?
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'skill',
    props:['skill']
}
</script>

<style>
    .skill{
        flex:1;
        width: 100%;
        padding: 25px;
    }
    .skill-inner{
        position: relative;
        padding: 25px;
        perspective: 1000px;
    }
    .skill-text-wrap{
        position: absolute;
        top:0;
        left:0;
        right:0;
        bottom:0;
        z-index: 0;
        overflow: hidden;
        perspective: 1000px;
    }
    .skill-text-wrap h2{
        /* color: #FFF; */
        font-size: 7vw;
        font-weight: 900;
        opacity: 0.2;
        transform-origin: center;
    }
    .skill-image-wrap{
        position:relative;
        z-index: 1;
        transform-origin: center;
    }
    .skill-image-wrap .image {
        width: 100%;
        filter: drop-shadow(0px 0px 12px rgba(0,0,0,0,0.25));
    }
    .skill-detail{
        /* color: #FFF; */
        padding: 25px;
        margin: 0px -25px -25px;
    }
    .skill-detail h2 {
        font-size: 24vh;
        font-weight: 700;
        /* color: #FFF; */
        margin-bottom: 15px;
    }
    .skill-detail p {
        font-size: 14px;
        line-height: 1.5;
        font-weight: 300;
        /* color: #FFF; */
    }
</style>