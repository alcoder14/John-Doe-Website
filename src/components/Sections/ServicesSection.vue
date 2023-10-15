<template>
    <section class="services-section">
        <div class="heading">
            <h1 class="section-title title-white">Services</h1>
            <div class="title-underline"></div>
        </div>
        <div class="container cards-and-button-container">

            <div class="services">
                <ServiceCard v-for="service in services" :key="service.title" :service="service" />
            </div>

            <div class="button-container">
                <button class="blue-transparent-btn" @click="this.$router.push({path: '/services'})"> <font-awesome-icon icon="fa fa-arrow-right" class="btn-icon" /> Read More</button>
            </div>

        </div>
    </section>
</template>

<script>

import ServiceCard from '../Cards/ServiceCard.vue'

export default {
    components: {
        ServiceCard
    },
    data(){
        return{
            services: [
                {
                    icon: "fa fa-table-cells",
                    title: "Digital Marketing",
                    content: "Tailored strategies to boost your online presence."
                },
                {
                    icon: "fa-solid fa-gear",
                    title: "SEO Optimization",
                    content: "Keyword research and optimization with continuous monitoring and improvement."
                },
                {
                    icon: "fa fa-arrow-trend-up",
                    title: "Content Strategy",
                    content: "Content planning and creation for blogs, websites, and social media."
                },
                {
                    icon: "fa fa-hashtag",
                    title: "Social Media Marketing",
                    content: "Social media audit and strategy development. Content creation and scheduling."
                },
                {
                    icon: "fa-solid fa-at",
                    title: "Email Marketing",
                    content: "Email campaign strategy and design with performance analytics."
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .services-section{
        background-color: $lightgrey;
    }
    .cards-and-button-container{
        @include flex-column();
        align-items: center;
    }
    .services{
        display: grid;
        grid-template-columns: repeat(5, 16%);
        justify-content: space-between;
        padding-bottom: 50px;
    }
    @media(max-width: 1300px){
        .services{
            grid-template-columns: repeat(3, 27%);
            row-gap: 3rem;
        }
    }
    @media(max-width: 1024px){
        .services{
            grid-template-columns: repeat(2, 45%);
            row-gap: 3rem;
        }
    }
</style>