<template>
<h2>hello</h2>
    <!-- <li v-for="contact in contactInfo" :key="contact"> -->
        <h3>{{ contact.method }}</h3>
    <!-- </li> -->
</template>

<script>
// import VueClipboard from 'vue-clipboard2'
export default {
    name: 'contact',
    props:['contact'],
    methods: {
        
    }
}
</script>