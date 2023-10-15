<template>
  <section id="phototext">
    <div class="heading">
        <h2 class="section-title title-grey">{{ data.title }}</h2>
        <div class="title-underline"></div>
    </div>
    <div class="container about-me">

        <p class="data-text">{{ data.description }}</p>

        <img :src="getImgUrl(data.image)" alt="my photo" class="photo" :class="{'photo-first': data.layout === 'image-first', 'photo-last': data.layout === 'image-last'}">

        <div class="data-achievements" v-if="data.awards">
            <div class="achievement">
                <font-awesome-icon icon="fa fa-school" class="achievement-icon" />
                <p>Bachelor's degree in Marketing from XYZ University</p>
            </div>
            <div class="achievement">
                <font-awesome-icon icon="fa fa-award" class="achievement-icon" />
                <p>Digital Marketing Award 2018</p>
            </div>
        </div>

        <button v-else class="blue-full-btn read-more-btn" @click="this.$router.push({path: '/portfolio'})"> <font-awesome-icon icon="fa fa-arrow-right" class="btn-icon" /> Read More</button>

    </div>
  </section>
</template>

<script>
export default {
    props: {
        data: Object
    },
    methods: {
        getImgUrl(img) {
            var images = require.context('../../assets/images/', false, /\.jpg$/)
            return images('./' + img + ".jpg")
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .about-me{
        display: grid;
        grid-template-columns: 50% 50%;
    }
    .photo{
        height: 500px;
        grid-row: 1 / span 2; 

    }
    .photo-last{
        grid-column-end: 3;
        justify-self: end;
    }
    .photo-first{
        grid-column-end: 2;
        justify-self: start;
    }
    .read-more-btn{
        align-self: start;
        justify-self: start;
    }

    .data-text{
        font-size: 3.4rem;
    }
    .data-achievements{
        @include flex-column();
    }
    .achievement{
        @include flex-row();
        font-size: 3rem;
        margin-top: 10px;
    }
    .achievement-icon{
        margin-right: 20px;
        align-self: center;
        color: $blue;
    }
    @media(max-width: 1800px){
        .data-text{
            font-size: 2.9rem;
        }
        .achievement{
            font-size: 2.8rem
        }
        .photo{
            height: 450px;
        }
    }
    @media(max-width: 1550px){
        .data-text{
            font-size: 2.5rem;
        }
        .achievement{
            font-size: 2.5rem;
        }
        .photo{
            height: 400px;
        }
    }
    @media(max-width: 1350px){
        .data-text{
            font-size: 2.1rem;
        }
        .achievement{
            font-size: 2.2rem;
        }
        .photo{
            height: 330px;
        }
    }
    @media(max-width: 1125px){
        .data-text{
            font-size: 1.8rem;
        }
        .achievement{
            font-size: 1.6rem;
        }
        .photo{
            height: 280px;
        }
    }
    @media(max-width: 970px){
        .about-me{
            grid-template-columns: 100%;
            height: fit-content;
        }
       .photo{
            grid-column: unset;
            width: 100%;
            height: auto;
            grid-column-end: 2;
            margin-bottom: 30px;
       }
       .data-text{
            font-size: 3.7vw;
            margin-bottom: 30px;
       }
       .achievement{
        font-size: 3.2vw;
       }
    }
</style>