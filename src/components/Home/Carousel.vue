<template>
    <div class="carousel">
        <slot :currentSlide="currentSlide"/>
        <!-- Navigation -->
        <div class="navigate">
            <div class="toggle-page left">
                <i @click="prevSlide" class="fas fa-chevron-left"></i>
            </div>
            <div class="toggle-page right">
                <i @click="nextSlide" class="fas fa-chevron-right"></i>
            </div>
        </div>

        <!-- Pagination -->
        <div class="pagination">
            <div class="pags">
                <span 
                @click="goToSlide(index)"
                v-for="(slide,index) in getSlideCount" 
                :key="index" 
                :class="{active: index +1 === currentSlide}">
                </span>
            </div>
        </div>
    </div>
</template>

<script>
import { ref, onMounted } from 'vue';
export default {
    name: 'project',
    props: ['project'],
    setup(props) {
        const currentSlide = ref(1);
        const getSlideCount = ref(null);
        const autoPlayEnabled = ref(true);
        const timeoutDuration = ref(5000);

        // next slide
        const nextSlide = () => {
            if(currentSlide.value === getSlideCount.value){
                currentSlide.value = 1;
                return;
            }
            currentSlide.value += 1;
        }

        // prev slide
        const prevSlide = () => {
            if (currentSlide.value === 1){
                currentSlide.value = 1;
                return;
            }
            currentSlide.value -= 1;
        }

        const goToSlide =(index) => {
            currentSlide.value = index + 1
        }

        // autoplay 
        const autoPlay = () => {
            setInterval(() => {
                nextSlide();
            }, timeoutDuration.value);
        }

        if (autoPlayEnabled.value) {
            autoPlay();
        }

    onMounted(() => {
        getSlideCount.value = document.querySelectorAll('.slide'+props.project.title).length;
        console.log(getSlideCount.value, props.project.title);
    });

        return { currentSlide, nextSlide, prevSlide, getSlideCount, goToSlide };
    },

}
</script>

<style>
    .navigate{
        padding: 0 10px;
        height: 100%;
        width: 100%;
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;

    }
    .toggle-page{
        display:flex;
        flex:1;

    }

    .right{
        justify-content: flex-end;
    }

    .navigate i {
        cursor: pointer;
        display:flex;
        align-items:center;
        justify-content: center;
        border-radius: 60%;
        width: 40px;
        height: 40px;
        background-color: rgb(61, 216, 255);
        color: #FFF;
    }

    .pagination{
        position: absolute;
        bottom: 5px;
        width: 100%;
        display: flex;
        gap: 10px;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
    .pags{
        display: flex;
        gap: 5px;
        justify-content: center;
        align-items: center;
        flex-direction: row;
    }

    .pagination span{
        cursor: pointer;
        width: 15px;
        height: 15px;
        border-radius: 50%;
        background-color: #fff;
        box-shadow: 0 1px 3px 0 rgba(0,0,0,0.1), 0 1px 2px 0 rgba(0,0,0,0.6);
    }

    .pagination .active {
        background-color: rgb(61, 216, 255);
    }

    
</style>