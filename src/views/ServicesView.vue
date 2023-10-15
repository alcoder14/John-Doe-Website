<template>
    <SmallHeader title="Services" />
    <section class="services">
        <div class="services-details-container container-w1400">
            <div class="navbar">
                <div v-for="service in services" :key="service" class="service" @click="selectService(service)" :class="{'selected-service': service === this.selectedService}" >
                    <p class="service-name" :class="{'selected-service-name': service === this.selectedService}">{{ service }}</p>
                </div>
            </div>
            <div class="service-data">
                <h2 class="service-title">{{ selectedService }}</h2>
                <p class="service-text">
                    {{ selectedServiceDescription }}
                </p>
            </div>
        </div>
    </section>

    <FooterSection />
</template>

<script>
import SmallHeader from '@/components/Sections/SmallHeader.vue';
import FooterSection from '@/components/Sections/FooterSection.vue';

export default {
    components: {
        SmallHeader,
        FooterSection
    },
    data(){
        return {
            services: ["Digital Marketing", "SEO Optimization", "Content Strategy", "Social Media Marketing", "Email Marketing"],
            selectedService: "Digital Marketing",
            selectedServiceDescription: null,
            digitalMarketing: "Digital marketing is a dynamic landscape where businesses leverage online channels to connect with their target audience. It encompasses a wide range of strategies, including SEO, content marketing, social media, email campaigns, and paid advertising. By harnessing the power of digital platforms, businesses can increase brand visibility, engage customers, and drive growth. It's a data-driven field where analytics and insights play a pivotal role in optimizing campaigns for success. In a rapidly evolving online world, digital marketing is a must for those seeking to stay competitive and adapt to changing consumer behaviors.",
            seoOptimization: "SEO (Search Engine Optimization) is the art and science of improving a website's visibility in search engine results. By optimizing on-page and off-page elements, such as keywords, meta tags, and backlinks, websites can climb the ranks on search engine result pages. A well-executed SEO strategy ensures that your content is discoverable by users seeking information or products relevant to your business. It's a long-term investment in organic traffic and, when done right, can lead to increased website traffic, brand authority, and ultimately, higher conversion rates.",
            contentStrategy: "Content strategy involves the creation, management, and distribution of valuable and relevant content to attract, engage, and convert a target audience. This encompasses various content types, from blog posts and articles to videos and infographics. A robust content strategy aligns with business goals, addresses the needs of the audience, and is optimized for search engines. It's not just about producing content but also ensuring it reaches the right people through the right channels. A well-crafted content strategy can establish authority, build trust, and drive user action.",
            smMarketing: "Social media marketing is the practice of using social platforms like Facebook, Instagram, Twitter, and LinkedIn to connect with an audience, build brand awareness, and drive business objectives. It involves creating and sharing content, engaging with followers, and running targeted advertising campaigns. The real power of social media lies in its ability to humanize brands and foster genuine connections. It can be a powerful tool for customer engagement, lead generation, and driving website traffic. Effective social media marketing requires a well-planned strategy, creative content, and continuous monitoring of performance metrics.",
            emailMarketing: "Email marketing is a direct and highly effective way to engage with a pre-existing audience or potential customers. It involves sending emails to a list of subscribers with the goal of building relationships, driving sales, or providing valuable information. Email campaigns can be segmented and personalized for maximum impact. They often include newsletters, product announcements, promotions, and follow-up sequences. Successful email marketing relies on delivering relevant content, compelling subject lines, and tracking open rates and click-through rates to refine strategies. It remains a cornerstone of digital marketing for nurturing customer relationships and driving conversions."

        }
    },
    mounted(){
        this.selectedServiceDescription = this.digitalMarketing
    },
    methods: {
        selectService(service){
            this.selectedService = service
            if(service === "Digital Marketing"){
                this.selectedServiceDescription = this.digitalMarketing
            } else if (service === "SEO Optimization"){
                this.selectedServiceDescription = this.seoOptimization
            } else if (service === "Content Strategy"){
                this.selectedServiceDescription = this.contentStrategy
            } else if (service === "Social Media Marketing"){
                this.selectedServiceDescription = this.smMarketing
            } else {
                this.selectedServiceDescription = this.emailMarketing
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .services{
        height: 50vh;
        background-color: $lightgrey;
    }
    .container-w1400{
        @include flex-row();
    }

    // Left Bar

    .navbar{
        width: 30%;
    }
    .service{
        font-size: 2.5rem;
        padding: 8px 14px;
        cursor: pointer;
        background-color: $darkgrey;
        color: $white;
        transition: all 0.3s;
    }
    .service:hover{
        border-left: solid 8px $blue;
    }
    .service-name{
        transition: transform 0.3s;
    }
    .service:hover .service-name{
        transform: translateX(10px);
    }

    .selected-service{
        border-left: solid 8px $blue;
    }
    .selected-service-name{
        transform: translateX(10px);
    }


    // Right Bar

    .service-data{
        width: 70%;
        padding: 0 30px;
    }
    .service-title{
        font-size: 4rem;
        color: $blue;
        margin-bottom: 20px;
    }
    .service-text{
        font-size: 2.4rem;
        color: $white;
    }

    // Responsiveness

    @media(max-width: 1250px){
        .service{
            font-size: 2.2rem;
        }
        .service-title{
            font-size: 3.6rem;
        }
        .service-text{
            font-size: 2.2rem;
        }
    }
    @media(max-width: 1024px){
        .service{
            font-size: 2rem;
        }
        .service-title{
            font-size: 3.3rem;
        }
        .service-text{
            font-size: 2rem;
        }
    }
    @media(max-width: 850px){

        .container-w1400{
            @include flex-column();
        }
        .services{
            height: fit-content;
        }
        .navbar{
            width: 100%;
            margin-bottom: 30px;
        }
        .service-data{
            width: 100%;
            padding: 0;
        }
        .service{
            font-size: 2rem;
        }
        .service-title{
            font-size: 3.3rem;
        }
        .service-text{
            font-size: 2rem;
        }
    }
</style>