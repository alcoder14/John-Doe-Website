<template>
    <div class="service-card" v-motion-slide-visible-bottom>
        <font-awesome-icon :icon="service.icon" class="card-icon" />
        <h2 class="service-title">{{ service.title }}</h2>
        <p class="service-content">{{ service.content }}</p>
    </div>
</template>

<script>
export default {
    props: {
        service: Object
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .service-card{
        height: 32vh;
        padding: 20px;
        background-color: $white;
        @include flex-column();
        justify-content: space-evenly;
        align-items: center;
    }
    .service-title, .service-content{
        text-align: center;
    }
    .card-icon{
        color: $blue;
        font-size: 7.5rem;
    }
    .service-title{
        font-size: 3rem;
        color: $darkgrey;
    }
    .service-content{
        font-size: 1.8rem;
    }
    @media(max-width: 1600px){
        .card-icon{
            font-size: 6.5rem;
        }
        .service-title{
            font-size: 2.6rem;
        }
        .service-content{
            font-size: 1.6rem;
        }
    }
    @media(max-width: 1300px){
        .card-icon{
            font-size: 7.5rem;
        }
        .service-title{
            font-size: 3rem;
        }
        .service-content{
            font-size: 1.8rem;
        }
    }
    @media(max-width: 1024px){
        .card-icon{
            font-size: 7.5rem;
        }
        .service-title{
            font-size: 3rem;
        }
        .service-content{
            font-size: 1.8rem;
        }
    }
    @media(max-width: 675px){
        .service-card{
            height: 25vh;
        }
        .card-icon{
            font-size: 7vw;
        }
        .service-title{
            font-size: 3.7vw;
        }
        .service-content{
            font-size: 3vw;
        }
    }
</style>