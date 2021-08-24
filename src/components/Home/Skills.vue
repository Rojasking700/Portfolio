<template>
    <div class="skill">
        <div class="skill-inner">
            <div class="skill-text-wrap" :style="StyleText">
                <h2 class="bg-text">{{ skill.bgtext }}</h2>
            </div>
            <div class="skill-image-wrap" :style="StyleImage">
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
    props:['skill'],
    data () {
      return {
        x: 0,
        y: 0,
        viewportHeight: 1,
        viewportWidth: 1
      }
    },
    created () {
      this.updateViewportSize()
    },

    mounted () {
      document.addEventListener('mousemove', this.onMouseMove)
      window.addEventListener('resize', this.updateViewportSize)
    },

    unmounted () {
      document.removeEventListener('mousemove', this.onMouseMove)
      window.removeEventListener('resize', this.updateViewportSize)
    },

    computed: {
      StyleText () {
        let r = percent(this.x, this.viewportWidth);
        let b = percent(this.y, this.viewportHeight);
        return {
        transform: `translateY(-${b}px) translateX(-${r}px)`
        }

        function percent (value, total) {
            return Math.round((value * 20 / total))
        }
      },
        StyleImage () {
            let r = percent(this.x, this.viewportWidth);
            let b =percent(this.y, this.viewportHeight);
            return {
                transform: `translateY(${b}px) translateX(${r}px) translateZ(100px)`
            }
            function percent (value, total) {
                return Math.round((value * 20 / total)) 
            }
        }
    },

    methods: {
      onMouseMove (ev) {
        this.x = ev.clientX
        this.y = ev.clientY
      },

      updateViewportSize () {
        this.viewportHeight = window.innerHeight
        this.viewportWidth = window.innerWidth
      }
    }
}

</script>

<style>
    .skill{
        /* flex: 0 0 33.3333%; */
        /* padding: 25px; */
        border: 2px solid #000;
        box-shadow:  0 4px 8px 0 rgba(0,0,0,0.2);
        border-radius: 10px;
        margin: 15px;
        min-width: 300px;
        max-width: 350px;

    }

    
    
    .skill-inner{
        position: relative;
        padding: 25px ;
        perspective: 1000px;
        margin: 20px;
    }
    .skill-text-wrap{
        position: absolute;
        display: flex;
        justify-content: center;
        top:0;
        left:0;
        right:0;
        bottom:0;
        z-index: 0;
        perspective: 1000px;
        transform-origin: center;
    }
    .bg-text{
        font-size: 3vw;
        font-weight: 900;
        opacity: 0.2;
    }
    .skill-image-wrap{
        display: flex;
        justify-content: center;
        position:relative;
        top: 0;
        left: 0;
        z-index: 1;
        transform-origin: center;
    }
    .skill-image-wrap img {
        width: 100px;
        filter: drop-shadow(0px 0px 12px rgba(0,0,0,0,0.25));
    }
    .skill-detail{
        align-items: center;
        margin: 50px 0px 0;
    }
    .skill-detail h2 {
        font-size: 24vh;
        font-weight: 700;
    }
    .skill-detail p {
        font-size: 14px;
        line-height: 1.5;
        font-weight: 300;
    }
    @media (max-width: 800px){
        .skill{
            min-width: 250px;
        }
        .skill-image-wrap img{
            min-width: 15vw;

        }
        .bg-text{
            font-size: 10vw;
        }
    }
    .skill:hover {
        transform: scale(1.09);
        transition-duration: 0.15s;
    }
</style>