<template>
  <nav class="navigation">
    <router-link to="/" class="link">Home</router-link>
    <router-link to="/services" class="link">Services</router-link>
    <router-link to="/portfolio" class="link">Portfolio</router-link>
    <router-link to="/contact" class="link">Contact</router-link>

    <button class="mobile-menu-btn open" @click="openMenu" v-if="!desktopMenuVisible"><font-awesome-icon icon="fa fa-bars" class="navbar-icon"/></button>

  </nav>

  <nav class="mobile-navigation" v-if="mobileMenuVisible" :class="{'openNavbar': animateOpening === true, 'closeNavbar': animateClosing === true}">
    <button class="mobile-menu-btn close" @click="closeMenu"><font-awesome-icon icon="fa fa-xmark" class="navbar-icon"/></button>
    <router-link to="/" class="mobile-link" @click="closeMenu">Home</router-link>
    <router-link to="/services" class="mobile-link" @click="closeMenu">Services</router-link>
    <router-link to="/portfolio" class="mobile-link" @click="closeMenu">Portfolio</router-link>
    <router-link to="/contact" class="mobile-link" @click="closeMenu">Contact</router-link>
  </nav>
  <router-view/>

</template>

<script>
  export default{
    mounted(){
      this.testScreenSize();
      window.addEventListener("resize", this.testScreenSize)
    },
    data(){
      return{
        mobileMenuVisible: false,
        desktopMenuVisible: true,
        animateOpening: false,
        animateClosing: false,
      }
    },

    methods: {
      toggleMenu(){
        this.mobileMenuVisible = !this.mobileMenuVisible

        // Add conditional class to trigger animation
        if(this.mobileMenuVisible){
          this.animateOpening = true
          setTimeout(() => {
              this.animateOpening = false
          }, 500);
        }
      },
      openMenu(){
        this.mobileMenuVisible = true
        this.animateOpening = true
          setTimeout(() => {
              this.animateOpening = false
          }, 500);
      },
      closeMenu(){
        this.animateClosing = true
          setTimeout(() =>{
            this.animateClosing = false
            this.mobileMenuVisible = false
          }, 500)
      },
      testScreenSize() {
        if(window.innerWidth <= 768){
          this.desktopMenuVisible = false
        } else {
          this.desktopMenuVisible = true,
          this.mobileMenuVisible = false
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import "@/assets/global.scss";

  // Desktop navigation
  .navigation{
    width: 100%;
    height: 10vh;
    background-color: $darkgrey;
    @include flex-row();
    justify-content: center;
    align-items: center;
    position: sticky;
    top: 0;
    z-index: 100;
  }
  .link{
    margin: 15px;
    font-size: 2.8rem;
    text-decoration: none;
    text-transform: uppercase;
    color: $blue;
  }
  .navbar-icon{
    font-size: 2rem;
  }

  // Mobile navigation
  .mobile-navigation{
      height: 100vh;
      width: 100%;
      background-color: rgba($color: $darkgrey, $alpha: 0.96);
      z-index: 10;
      position: fixed;
      top: 0;
      @include flex-column();
      justify-content: center;
      align-items: center;
  }
  .mobile-menu-btn{
    outline: 0;
    background-color: $darkgrey;
  }
  .open, .close{
    transition: 0.4s;
  }
  .open{
    border: $blue 3px solid;
    color: $blue;
    &:hover{
      background-color: $blue;
      color: $darkgrey;
    }
  }
  .close{
    border: $white 3px solid;
    color: $white;
    &:hover{
      background-color: $white;
      color: $darkgrey;
    }
    margin-bottom: 50px;
  }
  .mobile-link{
    text-decoration: none;
    font-size: 5rem;
    color: $blue;
    margin: 20px;
  }

  .openNavbar, .closeNavbar{
    animation-duration: 0.5s;
    animation-fill-mode: forwards;
  }

  .openNavbar{
    animation-name: slide-up;
    animation-timing-function: ease-out;
  }
  @keyframes slide-up{
    0%{transform: translateY(100%);}
    100%{transform: translateY(0%);}
  }

  .closeNavbar{
    animation-name: slide-down;
    animation-timing-function: ease-in;
  }
  @keyframes slide-down{
    0%{transform: translateY(0);}
    100%{transform: translateY(100%);}
  }
  

  // Responsive design

  @media(max-width: 1064px){
    .link{
      font-size: 2.4rem;
    }
  }
  @media(max-width: 768px){
    .link{
      display: none;
    }
  }
</style>
