<template>
  <div class="portfolio-card">
    <h1 class="mission">{{ project.mission }}</h1>
    <h3 class="client">{{ project.client }}</h3>
    <button class="show-more-btn" @click="this.$emit('openModal')">Show Details</button>
  </div>
</template>

<script>
export default {
    props: {
        project: Object
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .portfolio-card{
        background-color: $white;
        height: 30vh;
        padding: 20px;
        @include flex-column();
        justify-content: space-evenly;
        align-items: center;
    }
    .mission, .client{
        text-align: center;
    }
    .mission{
        font-size: 2.2rem;
    }
    .client{
        font-size: 1.7rem;
        color: $lightgrey;
    }
    .show-more-btn{
        background-color: $blue;
        color: $white;
        border: none;
        font-size: 1.6rem;
    }
    @media(max-width: 1375px){
        .mission{
            font-size: 1.9rem;
        }
        .client{
            font-size: 1.5rem;
        }
        .show-more-btn{
            font-size: 1.4rem;
        }
    }
    @media(max-width: 1125px){
        .mission{
            font-size: 1.7rem;
        }
        .client{
            font-size: 1.3rem;
        }
        .show-more-btn{
            font-size: 1.1rem;
        }
    }
    @media(max-width: 1024px){
        .mission{
            font-size: 2.2vw;
        }
        .client{
            font-size: 1.7vw;
        }
        .show-more-btn{
            font-size: 1.5vw;
        }
    }
    @media(max-width: 1024px){
        .mission{
            font-size: 3vw;
        }
        .client{
            font-size: 2.2vw;
        }
        .show-more-btn{
            font-size: 2.3vw;
        }
    }
</style>