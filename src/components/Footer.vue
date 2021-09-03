<template>
    <footer>
        <div class="footer">
        <div class="lets-talk">
            <h1>Let's Talk</h1>
            <p>Feel free to contact me about any questions you may have about me or my experience. If you find any bugs or have any suggestions about the site please let me know so I can improve and make this a better place.  </p>
            <router-link class="footer-btn" :to="{name: 'Contact'}">Contact Me</router-link>
        </div>
        <div class="footer-contact">
            <div class="footer-lists">
                <ul class="footer-span" id="footer-left-contact">
                    <li v-for="contact in contactInfo" :key="contact">
                        <h3>{{ contact.method }}</h3>
                    </li>
                </ul>
                <ul class="footer-span" >
                    <li v-for="contact in contactInfo" :key="contact">
                        <h3 title="copy">{{ contact.contact }}</h3>
                    </li>
                </ul>
            </div>
            <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
            <div class="footer-container">
                <div class="effect thurio">
                    <div class="buttons">
                    <!-- <a href="#" class="fb" title="Join us on Facebook"><i class="fa fa-facebook" aria-hidden="true"></i></a> -->
                    <!-- <a href="#" class="tw" title="Join us on Twitter"><i class="fa fa-twitter" aria-hidden="true"></i></a> -->
                    <!-- <a href="#" class="g-plus" title="Join us on Google+"><i class="fa fa-google-plus" aria-hidden="true"></i></a> -->
                    <!-- <a href="#" class="dribbble" title="Join us on Dribbble"><i class="fa fa-dribbble" aria-hidden="true"></i></a> -->
                    <!-- <a href="#" class="vimeo" title="Join us on Vimeo"><i class="fa fa-vimeo" aria-hidden="true"></i></a> -->
                    <!-- <a href="#" class="pinterest" title="Join us on Pinterest"><i class="fa fa-pinterest-p" aria-hidden="true"></i></a> -->
                    <a href="https://github.com/Rojasking700" class="github" title="Join us on Github"><i class="fa fa-github" aria-hidden="true"></i></a>
                    <a href="https://www.linkedin.com/in/gabriel-rojas-81ab90199/" class="in" title="Join us on Linked In"><i class="fa fa-linkedin" aria-hidden="true"></i></a>
                    </div>
                </div>
            </div>
        </div>
        </div>
    </footer>
</template>

<script>
// import VueClipboard from 'vue-clipboard2'
export default {
    name: 'contactInfo',
    props:['contactInfo'],
    methods: {
        
    }
}
</script>

<style>
    footer{
        background: black;
        width: 100%;
        display: flex;
        justify-content: center;
        margin-top:auto;
        position: absolute;
        bottom: 0;
        height: 30vh;
    }
    .footer{
        display: flex;
        justify-content: space-around;
        flex-direction: row;
        color: #fff;
        width: 80%;
        padding: 40px 20px;
        align-items: center;
    }
    .lets-talk{
        max-width: 40%;
    }
    .lets-talk p{
        font-family: 'Montserrat', sans-serif;
        font-weight: 900;
        padding: 15px 0;
    }
    .footer-contact{
        max-width:100%;
        display: flex;
        justify-content: space-between;
        flex-direction: column;
    }
    .footer-lists{
        display: flex;
        /* justify-content: space-between; */
        flex-direction: row;
    }
    .footer-span{
        /* width: 100%; */
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding: 20px;
    }
    #footer-left-contact{
        padding-left: 0;
    }
    
    .footer-span li{
        padding: 5px 0;
    }

    .footer-btn {
        position: relative;
        display: flex;
        justify-content: center;
        width: 150px;
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

    .footer-btn:hover {
        color: #333;
        background-color: rgb(61, 216, 255);
        box-shadow: 5px 5px #666;
        
        transition: 0.15s ease;
    }
    /* ------------------------------------------------------------------------------------- */
    .footer-container {
        display: flex;
        justify-content: center;
    }

.effect .buttons {
  display: flex;
  justify-content: center;
}

/* styles for a common effect !!!YOU NEED THEM */

.effect {
  display: flex; 
}
.effect a {
  text-decoration: none !important;
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  margin-right: 20px;
  font-size: 25px;
  overflow: hidden;
  position: relative;
  color: rgb(61, 216, 255);
  border: 2px solid rgb(61, 216, 255);
}
.effect a i {
  position: relative;
  z-index: 3;
}
.effect a:last-child {
  margin-right: 0px;
}
.effect a:before {
  content: "";
  display: inline-block;
  height: 100%;
  vertical-align: middle;
}
.effect a i {
  display: inline-block;
  vertical-align: middle;
}

 .effect.thurio a {
  transition: border-radius 0.2s linear 0s;
  transform: rotate(45deg);
}
.effect.thurio a i {
  transition: transform 0.01s linear 0s;
  transform: rotate(-45deg);
}
.effect.thurio a:hover {
  border-radius: 0px;
  box-shadow: 0px 0px 16px 4px rgba(61, 216, 255, 1);
  transition: 0.3s ease-out;
  transform: scale(1.2) rotate(45deg);
}

@media (max-width: 800px){
    footer{
        height: 60vh;

    }
    .footer{
        flex-direction: column;
    }
    .lets-talk{
        max-width: 100%;
        display: flex;
        flex-direction: column;
        /* justify-content: center; */
        align-items: center;
        padding-bottom: 20px;
    }
    .footer-span{
        padding:5px;
    }
    
}
</style>