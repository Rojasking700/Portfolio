<template>
  <div class="wrapper">
    <div class="box">
      <div class="inner-box">
        <div class="circle" :style="styles" />
        <div class="circle2" :style="styles2"></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
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
      styles () {
        //   console.log(this.x,this.y)
        return {
          left: percent(this.x, this.viewportWidth),
          top: percent(this.y, this.viewportHeight)
        }

        function percent (value, total) {
            return Math.round((value * 100 / total)) + '%'
        }
      },
        styles2 () {
            return {
            right: percent(this.x, this.viewportWidth),
            bottom: percent(this.y, this.viewportHeight)
            }
            function percent (value, total) {
                return Math.round((value * 100 / total)) + '%'
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
  .wrapper {
    width: 0;
    height: 0;
    position: fixed;
    left: 50vw;
    top: 50vh;
  }

  .box {
    width: 100px;
    height: 100px;
    border: 2px solid #000;
    position: relative;
    left: -50px;
    top: -50px;
  }

  .inner-box {
    position: absolute;
    top: 0;
    bottom: 10px;
    left: 0;
    right: 10px;
  }

  .circle {
    background: #009;
    border-radius: 5px;
    position: absolute;
    height: 10px;
    width: 10px;
    margin-right: -10px;
  }
  .circle2 {
    background: rgb(153, 0, 0);
    border-radius: 5px;
    position: absolute;
    height: 10px;
    width: 10px;
    margin-right: -10px;
  }
</style>