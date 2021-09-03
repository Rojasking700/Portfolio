<template>
<div class="contact-card" type="button" @click="copy">
    <h1>{{ contact.method }}:</h1>
    <h2>{{ contact.contact }}</h2>

</div>
</template>

<script>
// import VueClipboard from 'vue-clipboard2'
// import { copyText } from 'vue3-clipboard';

export default {
    name: 'contact',
    props:['contact'],
    methods: {
        copy(){
            // try{
                console.log('text copied')
                navigator.clipboard.writeText('hello');
            // }catch(e){
                // throw e
            // }
        }
    },
    setup() {
    //     const message = 'Hello Clipborad!'
    //   const onCopy = (e) => {
    //     alert('You just copied: ' + e.text)
    //   }
    //   const onError = () => {
    //     alert('Failed to copy texts')
    //   }
 
    //   return { message, onCopy, onError }
//       const doCopy = () => {
//         copyText('Hello Clipborad', undefined, (error, event) => {
//           if (error) {
//             alert('Can not copy')
//             console.log(error)
//           } else {
//             alert('Copied')
//             console.log(event)
//           }
//         })
//       }
 
//       return { doCopy }
    },
  }
</script>

<style>
.contact-card{
    /* margin: 20px; */
    /* padding: 20px; */
    color: #fff;
    /* min-width: 320px;
    max-width: 320px; */
    width:320px;
    height: 250px;
    background: rgba(0,0,0,0.2);
    border: 15px solid rgba(255,255,255,0.5);
    border-bottom: 15px solid rgba(0,0,0,0.5);
    border-right: 15px solid rgba(0,0,0,0.5);
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    transition: 0.25s ease-out;
}
.contact-card h1{
    font-size: 1.75rem;
    text-shadow:2px 4px 4px rgb(0, 0, 0);
    transition: 0.25s ease-out;
}

.contact-card:hover{
    transform: scale(1.1);
    transition: 0.25s ease-out;
    background: rgba(0,0,0,0.7);
    border: 15px solid rgba(180, 180, 180, 0.7);
    border-bottom: 15px solid rgba(0,0,0,0.7);
    border-right: 15px solid rgba(0,0,0,0.7);
}
.contact-card:hover h1{
    text-shadow:2px 2px 0px rgb(100, 100, 100);
    transition: 0.25s ease-out;
}
.contact-card:hover h2{
    text-shadow:2px 2px 0px rgb(100, 100, 100);
    transition: 0.25s ease-out;
}
@media (max-width: 1220px){
    .contact-card{
        height: 150px;
        }
    }
@media (max-width: 400px){
    .contact-card{
        width: 250px;
        
    transition: 0.25s ease-out;
    }
    .contact-card h2{
    font-size: 1.3em;
    transition: 0.25s ease-out;
}
}
</style>