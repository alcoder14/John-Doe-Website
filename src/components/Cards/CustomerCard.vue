<template>
    <div class="customer-card" v-motion-slide-visible-bottom>
        <div class="photo-quotes">
            <font-awesome-icon icon="fa fa-quote-left" class="quote" />
            <img :src="getImgUrl(customer.img)" alt="customer" class="customer-img">
            <font-awesome-icon icon="fa fa-quote-right" class="quote" />
        </div>
        <p class="customer-review">{{ customer.review }}</p>
        <h3 class="customer-name">{{ customer.name }}, {{ customer.age }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    props: {
        customer: Object
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
        .customer-card{
            width: 25%;
            padding: 30px;
            height: 37vh;
            background-color: $white;
            @include flex-column();
            justify-content: space-between;
            text-align: center;
        }
        .photo-quotes{
            @include flex-row();
            justify-content: space-evenly;
            align-items: center;
        }
        .customer-img{
            height: 120px;
            width: auto;
        }
        .quote{
            font-size: 3rem; 
            color: $blue;  
        }
        .customer-review{
            font-size: 1.6rem;
        }
        .customer-name{
            font-size: 1.9rem;
            color: $blue;
        }

        @media(max-width: 1230px){
            .customer-card{
                width: 28%;
            }
            .customer-img{
                height: 110px;
                width: auto;
            }
            .quote{
                font-size: 2.8rem; 
                color: $blue;  
            }
            .customer-review{
                font-size: 1.4rem;
            }
            .customer-name{
                font-size: 1.7rem;
                color: $blue;
            }
        }
        @media(max-width: 900px){
            .customer-card{
                width: 100%;
                margin-bottom: 30px;
            }
            .customer-img{
                height: 130px;
                width: auto;
            }
            .quote{
                font-size: 6vw; 
                color: $blue;  
            }
            .customer-review{
                font-size: 2.7vw;
            }
            .customer-name{
                font-size: 2.5vw;
                color: $blue;
            }
        }
        @media(max-width: 900px){
            .quote{
                font-size: 8vw; 
                color: $blue;  
            }
            .customer-review{
                font-size: 3.4vw;
            }
            .customer-name{
                font-size: 3.5vw;
                color: $blue;
            }
        }
  </style>