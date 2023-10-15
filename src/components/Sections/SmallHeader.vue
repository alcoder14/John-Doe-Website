<template>
    <header class="header">
        <h1 class="small-header-title">{{ title }}</h1>
    </header>
</template>

<script>
export default {
    props:{
        title: String
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .header{
        background-image: url("../../assets/images/bgphoto2.png");
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        height: 30vh;
        @include flex-row();
        justify-content: center;
        align-items: center;
    }
    .small-header-title{
        font-size: 6rem;
        color: $white;
    }
    @media(max-width: 768px){
        .header{
            height: 20vh;
        }
        .small-header-title{
            font-size: 4rem;
        }   
    }
</style>