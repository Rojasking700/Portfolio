<template>
    <div class="iam-container">
        <h1 class="h1-iam">Hello,
            <span class="typed-text">{{ typeValue }}</span>
            <span class="cursor" :class="{'typing': typeStatus}">&nbsp;</span>
        </h1>
    </div>
</template>

<script>
import { setTimeout } from 'timers';

export default {
    data: () => {
        return {
            typeValue: '',
            typeStatus: false,
            typeArray: ["I develop websites","these are my skills:"],
            typingSpeed: 200,
            erasingSpeed: 200,
            newTextDelay: 2000,
            typeArrayIndex: 0,
            charIndex: 0
        }
    },
    methods: {
        typeText() {
            if(this.charIndex < this.typeArray[this.typeArrayIndex].length) {
                if(!this.typeStatus)
                    this.typeStatus = true;
                this.typeValue += this.typeArray[this.typeArrayIndex].charAt(this.charIndex);
                this.charIndex += 1;
                setTimeout(this.typeText, this.typingSpeed);
            }else{
                this.typeStatus = false;
                setTimeout(this.eraseText, this.newTextDelay);
            }
        },
        eraseText() {
            if(this.charIndex > 0) {
                if(!this.typeStatus)
                    this.typeStatus= true;
                this.typeValue = this.typeArray[this.typeArrayIndex].substring(0, this.charIndex -1);
                this.charIndex -=1;
                setTimeout(this.eraseText, this.erasingSpeed);
            }else{
                this.typeStatus = false;
                this.typeArrayIndex += 1;
                if(this.typeArrayIndex >= this.typeArray.length)
                    this.typeArrayIndex =0;
                setTimeout(this.typeText, this.typingSpeed + 1000);
            }
        }
    },
    created() {
        setTimeout(this.typeText, this.newTextDelay + 200);
    }
}
</script>
<style>
    .iam-container {
        margin-top: 5rem;
        margin-bottom: 1rem;
        display: flex;
        justify-content: center;
        align-items: center;
        /* width: 80%; */
    }
    .h1-iam {
        font-size: 5rem;
        font-weight: 200;
        text-align: center;
    }
    .typed-text{
        color:red;
    }
    .cursor{
        display: inline-block;
        margin-left: 3px;
        width: 4px;
        background-color: black;
        animation: cursorBlink 1s infinite;
    }
    .cursor.typing{
        animation:none;
    }
    @keyframes cursorBlink {
        49% { background-color: black; }
        50% { background-color: transparent;}
        99% { background-color: transparent;}
    }
    @media (max-width: 800px){
        .h1-iam{
            font-size: 3rem;
        }
    }
</style>