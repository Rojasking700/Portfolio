<template>
    <footer>
        <div class="footer">
        <div class="lets-talk">
            <h1>Let's Talk</h1>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Praesentium amet alias nulla commodi delectus consequuntur necessitatibus mollitia eligendi explicabo suscipit.</p>
        </div>
        <div class="footer-contact">
            <ul class="footer-span">
                <li v-for="contact in contactInfo" :key="contact">
                    <h3>{{ contact.method }}</h3>
                </li>
            </ul>
            <ul class="footer-span">
                <li v-for="contact in contactInfo" :key="contact">
                    <h3>{{ contact.contact }}</h3>
                </li>
            </ul>
        </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'contactInfo',
    props:['contactInfo'],
}
</script>

<style>
    footer{
        background: black;
        width: 100%;
        display: flex;
        justify-content: center;
    }
    .footer{
        display: flex;
        justify-content: space-around;
        flex-direction: row;
        color: #fff;
        /* position: absolute; */
        width: 80%;
        padding: 40px 20px;
        align-items: center;
    }
    .lets-talk{
        max-width: 30%;
    }
    .footer-contact{
        max-width:100%;
        display: flex;
        justify-content: space-between;
        /* flex-direction: column; */
    }
    .footer-span{
        /* width: 100%; */
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding: 20px;
    }
    .footer-span li{
        padding: 5px 0;
    }

</style>