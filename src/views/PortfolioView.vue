<template>
    <SmallHeader title="Portfolio" />
    <section class="portfolio">
        <div class="container-w1400">
            <p class="text">Here are some of the best of my projects: </p>
            <div class="projects-container">
                <PortfolioCard v-for="project in projects" :key="project.client" :project="project" @openModal="toggleModal($event)" />
            </div>
        </div>
    </section>
    <FooterSection />

    <div class="modal-container" v-if="modalVisible" @click="closeModal">
        <div class="modal-content">

            <button class="portfolio-close-btn close" @click="toggleModal"><font-awesome-icon icon="fa fa-xmark" class="navbar-icon"/></button>

            <p class="label">Client</p>
            <h2 class="client">Company X, an e-commerce fashion retailer</h2>
            <p class="label">Objective</p>
            <h3 class="objective">Improve organic search rankings and drive more traffic to the website.</h3>
            <p class="label">Actions Taken</p>
            <ul class="actions-list">
                <li>Conducted an extensive keyword research and competitive analysis.</li>
                <li>Optimized on-page content, meta tags, and product descriptions.</li>
                <li>Implemented a link-building strategy to increase domain authority.</li>
                <li>Created an XML sitemap and submitted it to search engines.</li>
                <li>Monitored and adjusted the strategy based on analytics data.</li>
            </ul>
            <p class="label">Results</p>
            <ul class="results-list">
                <li>Within 6 months, organic traffic increased by 45%.</li>
                <li>Significant improvement in keyword rankings.</li>
                <li>20% increase in online sales attributed to organic search.</li>
            </ul>
        </div>
    </div>

</template>

<script>

import SmallHeader from '@/components/Sections/SmallHeader.vue';
import FooterSection from '@/components/Sections/FooterSection.vue';
import PortfolioCard from '@/components/Cards/PortfolioCard.vue';

export default {
    components: {
        SmallHeader,
        FooterSection,
        PortfolioCard
    },
    methods: {
        toggleModal(){
            this.modalVisible = !this.modalVisible
        },
        closeModal(e){
            console.log(e.target)
            if(e.target === e.currentTarget){
                this.toggleModal()
            }
        }
    },
    data(){
        return{
            modalVisible: false,
            projects: [
                {
                    mission: "Increase sales and customer retention through targeted email marketing campaigns.",
                    client: "Fashion E-commerce Brand",
                },
                {
                    mission: "Improve organic search rankings and drive more traffic to the website.",
                    client: " Company X, an e-commerce fashion retailer",
                },
                {
                    mission: "Generate immediate sales and brand awareness for the new product line.",
                    client: "E-commerce Startup",
                },
                {
                    mission: "Enhance brand authority and establish the client as an industry thought leader.",
                    client: "B2B Software Solutions Provider",
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .portfolio{
        height: 50vh;
        background-color: $lightgrey;
    }
    .projects-container{
        display: grid;
        grid-template-columns: repeat(4, 20%);
        justify-content: space-between;
    }
    .text{
        font-size: 2rem;
        margin-bottom: 20px;
        color: $white;
    }

    .modal-container{
        z-index: 200;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        @include flex-row();
        justify-content: center;
        align-items: center;
        background-color: rgba($color: $darkgrey, $alpha: 0.96);
        .modal-content{
            width: 700px;
            background-color: $white;
            padding: 30px;
        }
    }

    .label{
        font-size: 2rem;
        margin-bottom: 10px;
    }
    .client, .objective{
        font-size: 2.8rem;
        margin-bottom: 20px;
    }
    .actions-list{
        margin-bottom: 20px;
    }
    li{
        font-size: 1.6rem;
        list-style-position: inside;
    }

    .portfolio-close-btn{
        outline: 0;
        background-color: $white;
    }

    .close{
        transition: 0.4s;
        border: $darkgrey 3px solid;
        color: $darkgrey;
        &:hover{
            background-color: $darkgrey;
            color: $white;
        }
        margin-bottom: 20px;
    }


    @media(max-width: 1024px){
        .projects-container{
            grid-template-columns: repeat(2, 50%);
            row-gap: 20px;
            column-gap: 20px;
        }
        .portfolio {
            height: fit-content;
        }
    }

    @media(max-width: 768px){
        .modal-container{
            .modal-content{
                width: 100%;
                height: 100vh;
                background-color: $white;
                padding: 30px;
            }
        }
    }
</style>