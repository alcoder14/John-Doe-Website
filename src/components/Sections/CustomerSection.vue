<template>
  <section class="customer-reviews-container">
    <div class="heading">
        <h2 class="section-title title-white">Customer Reviews</h2>
        <div class="title-underline"></div>
    </div>
    <div class="container-w1300 customer-reviews">
        <CustomerCard v-for="customer in customers" :key="customer.name" :customer="customer" />
    </div>
  </section>
</template>

<script>

import CustomerCard from '../Cards/CustomerCard.vue';

export default {
    components: {
        CustomerCard
    },
    data(){
        return{
            customers: [
                {
                    img: "profile1",
                    review: "Working with John Doe was a game-changer for my online business. Their expertise in SEO took my website from obscurity to the top of search results, resulting in a significant boost in sales.",
                    name: "James",
                    age: 33
                },
                {
                    img: "profile2",
                    review: "Working with John Doe was a game-changer for my online business. Their expertise in SEO took my website from obscurity to the top of search results, resulting in a significant boost in sales.",
                    name: "Sarah",
                    age: 25
                },
                {
                    img: "profile3",
                    review: "Working with John Doe was a game-changer for my online business. Their expertise in SEO took my website from obscurity to the top of search results, resulting in a significant boost in sales.",
                    name: "Michael",
                    age: 29
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .customer-reviews-container{
        background-color: $lightgrey;
    }
    .customer-reviews{
        @include flex-row();
        justify-content: space-between;
    }
    .container-w1300{
        max-width: 1300px;
        margin-left: auto;
        margin-right: auto;
        padding: 50px 0;
    }
    @media(max-width: 1400px){
        .container-w1300{
            max-width: unset;
            margin: unset;
            padding: 50px;
            width: 100%;
        }
    }
    @media(max-width: 900px){
        .customer-reviews{
            @include flex-column();
        }
    }

</style>