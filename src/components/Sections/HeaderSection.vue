<template>
    <header class="header">
      <h1 class="name">John Doe</h1>
      <h2 class="title">Marketing consultant</h2>
      <button class="blue-transparent-btn" @click="scrollDown"> <font-awesome-icon icon="fa fa-arrow-down" class="btn-icon" /> Get Started</button>
  </header>
  <section class="short-description">
    <p>A passionate marketing professional with over 10 years of experience in helping businesses grow their online presence. I specialize in digital marketing strategies, SEO, and content marketing.</p>
  </section>
  </template>
  
  <script>
  export default {
    methods: {
      scrollDown(){
        // auto scroll down to first phototext section when a button is clicked

        document.querySelector("#phototext").scrollIntoView({ behavior: 'smooth'})
      }
    }
  }
  </script>
  
  <style lang="scss" scoped>
  @import "@/assets/global.scss";
  .header{
    height: 70vh;
    width: 100%;
    @include flex-column();
    justify-content: center;
    align-items: center;
    background-image: url("../../assets/images/bgphoto.png");
    background-size: 100%;
    background-repeat: no-repeat;
    background-position: center;
  }
  .name{
    font-size: 15rem;
    color: $white;
  }
  .title{
    font-size: 5rem;
    font-weight: lighter;
    color: white;
    margin-bottom: 2rem;
  }
  .short-description{
    width: 100%;
    height: 20vh;
    padding: 0 200px;
    @include flex-row();
    justify-content: center;
    align-items: center;
    text-align: center;
    font-size: 3.4rem;
  }

  @media(max-width: 1600px){
    .header{
      background-size: cover;
    }
  }
  @media(max-width: 1440px){
    .name{
      font-size: 12rem;
    }
    .title{
      font-size: 3.8rem;
    }
    .short-description{
      font-size: 2.4rem;
      padding: 0 150px;
    }
  }
  @media(max-width: 1000px){
    .short-description{
      padding: 0 80px;
    }
  }
  @media(max-width: 768px){
    .name{
      font-size: 9rem;
    }
    .title{
      font-size: 3rem;
    }
  }
  @media(max-width: 626px){
    .short-description{
        font-size: 1.6rem;
        padding: 0 50px;
    }
    .name{
      font-size: 7rem;
    }
    .title{
      font-size: 2rem;
    }
  }
</style>