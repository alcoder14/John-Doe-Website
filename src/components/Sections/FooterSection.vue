<template>
  <footer>
    <div class="left-block">
        <div class="footer-info">
            <font-awesome-icon icon="fa fa-location-dot" class="icon" />
            <p>New York City</p>
        </div>
        <div class="footer-info">
            <font-awesome-icon icon="fa fa-at" class="icon" />
            <p>info@johndoe.com</p>
        </div>
        <div class="footer-info">
            <font-awesome-icon icon="fa fa-phone" class="icon" />
            <p>(555) 555-5555</p>
        </div>
    </div>
    <div class="right-block">
        <div class="footer-info">
            <a href="#"><font-awesome-icon icon="fa-brands fa-instagram" class="brand-icon" /></a>
            <a href="#"><font-awesome-icon icon="fa-brands fa-youtube" class="brand-icon" /></a>
            <a href="#"><font-awesome-icon icon="fa-brands fa-facebook" class="brand-icon" /></a>
        </div>
        <div class="footer-line"></div>
        <div class="footer-name">© 2023 John Doe</div>
    </div>
  </footer>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    footer{
        @include flex-row();
        justify-content: center;
        align-items: center;
        background-color: $darkgrey;
    }
    .left-block, .right-block{
        height: 15vh;
        margin: 50px;
        @include flex-column();
        justify-content: space-between;
    }
    .footer-info, .footer-line, .footer-name{
        font-size: 3rem;
        @include flex-row();
    }
    .footer-info{
        @include flex-row();
    }
    .footer-line{
        background-color: $lightgrey;
        height: 2rem;
        width: 200px;
    }
    .icon{
        margin-right: 10px;
    }
    .brand-icon{
        font-size: 4rem;
        margin-right: 10px;
    }
    .icon, .brand-icon{
        color: $blue;
    }
    p, .footer-name{
        color: $white;
    }
    @media(max-width: 1250px){
        .footer-info, .footer-line, .footer-name{
            font-size: 2.4rem;
        }
        .brand-icon{
            font-size: 3rem;
        }
        .footer-line{
            height: 1rem;
            width: 100%;
        }
    }
    @media(max-width: 768px){
        footer{
            padding: 30px;
        }
        .left-block, .right-block{
            margin: 20px;
            height: 12vh;
        }
        .footer-info, .footer-line, .footer-name{
            font-size: 2.4rem;
        }
        .brand-icon{
            font-size: 3rem;
        }
    }
    @media(max-width: 568px){
        .left-block, .right-block{
            margin: 14px;
            height: 11vh;
        }
        .footer-info, .footer-line, .footer-name{
            font-size: 1.8rem;
        }
        .brand-icon{
            font-size: 2.4rem;
        }
    }
</style>