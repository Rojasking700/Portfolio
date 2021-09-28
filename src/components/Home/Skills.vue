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
                <h3>{{ skill.title }}:</h3>
                <p>
                    {{ skill.detail }}
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
    @import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');
    .skill{
        /* flex: 0 0 33.3333%; */
        /* padding: 25px; */
        /* border: 2px solid #000; */
        box-shadow:  0 4px 8px 0 rgba(0,0,0,0.2);
        border-radius: 10px;
        margin: 25px;
        min-width: 350px;
        max-width: 350px;
        transition: 0.25s ease-out;
        background: rgb(255,255,255);
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
        font-size: 3.5rem;
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
        height: 100px;
        /* filter: drop-shadow(0px 0px 12px rgba(0,0,0,0,1)); */
    }
    .skill-detail{
        align-items: center;
        margin: 50px 0px 0;
    }
    .skill-detail h3{
        font-size: 1.3rem;
        font-weight: 100;
    }
    .skill-detail p {
        font-family: 'Montserrat', sans-serif;
        font-size: 1rem;
        line-height: 1.5;
        font-weight: medium;
        padding: 10px 0;
    }
    #disabled-btn{
        padding: 0;
        padding-top: 7px;
        margin: 0;
    }
    .skill:hover {
        transform: scale(1.09);
        transition: 0.25s ease-out;
        box-shadow:  0 8px 16px 0 rgba(0,0,0,0.4);
        overflow:auto;
    }

    .skill-btn {
        position: relative;
        display: flex;
        justify-content: center;
        width: 60%;
        /* display: inline-block; */
        padding: 15px 5px;
        font-size: 1.3rem;
        cursor: pointer;
        text-align: center;
        text-decoration: none;
        color: #fff;
        background-color: rgb(0, 120, 180);
        box-shadow: 5px 5px #bbb;
        border: none;
        border-radius: 3px;
        transition: 0.15s ease;
    }  

    .skill-btn:hover {
        color: #333;
        background-color: rgb(61, 216, 255);
        box-shadow: 5px 5px #666;
        
        transition: 0.15s ease;
    }
    .skill-btn:active {
        color: #000;
        background-color: #eee;
        box-shadow: 2px 2px #666;
        transform: translateY(3px);
        transition: 0.01s ease;
    }

    @media (max-width: 800px){
        .skill{
            min-width: 300px;
        }
        .bg-text{
            font-size: 3rem;
        }
        .skill-btn{
            font-size: 1rem;
            padding: 1rem 1rem;
            width:70%;
        }
    }


    
</style>