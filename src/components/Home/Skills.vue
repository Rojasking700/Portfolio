<template>
    <div class="skill">
        <div class="skill-inner">
            <div class="skill-box">
                <div class="skill-inner-box">
                    <div class="skill-text-wrap" :style="StyleText">
                        <h2 class="bg-text">{{ skill.bgtext }}</h2>
                    </div>
                    <div class="skill-image-wrap" :style="StyleImage">
                        <img class="image" :src="skill.src">
                    </div>
                </div>
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
        //   console.log(this.x,this.y)
        let r = percent(this.x, this.viewportWidth);
        let b = percent(this.y, this.viewportHeight);
        return {
        transform: `translateY(-${b}px) translateX(-${r}px) translateZ(100px)`
        //   left: percent(this.x, this.viewportWidth),
        //   top: percent(this.y, this.viewportHeight)
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
            // right: percent(this.x, this.viewportWidth),
            // bottom: percent(this.y, this.viewportHeight)
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
        /* overflow: hidden; */
        perspective: 1000px;
    }
    .skill-text-wrap h2{
        /* color: #FFF; */
        font-size: 3vw;
        font-weight: 900;
        opacity: 0.2;
        /* transform-origin: center; */
    }
    .skill-image-wrap{
        position:absolute;
        z-index: 1;
        transform-origin: center;
    }
    .skill-image-wrap .image {
        width: 6vw;
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