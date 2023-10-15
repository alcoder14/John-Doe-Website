<template>
    <SmallHeader title="Contact" />
    <section class="contact">
        <form class="contact-form container-w900">
            <input type="text" placeholder="Email" class="input" v-model="formData.email">
            <input type="text" placeholder="Subject" class="input" v-model="formData.subject">
            <input type="text" placeholder="First Name" class="input" v-model="formData.firstName">
            <input type="text" placeholder="Last Name" class="input" v-model="formData.lastName">
            <textarea placeholder="Message" cols="30" rows="10" class="input" v-model="formData.message"></textarea>
            <button type="button" class="blue-full-btn-no-effect contact-btn">Send</button>
            <button type="button" class="grey-full-btn contact-btn" @click="resetData">Clear</button>
        </form>
    </section>
</template>

<script>

import SmallHeader from './SmallHeader.vue';

export default {
    components: {SmallHeader},
    data(){
        return{
            formData: {
                email: "",
                subject: "",
                firstName: "",
                lastName: "",
                message: ""
            }
        }
    },
    methods: {
        resetData(){
            this.formData.email = ""
            this.formData.subject = ""
            this.formData.firstName = ""
            this.formData.lastName = ""
            this.formData.message = ""
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "@/assets/global.scss";
    .contact{
        height: 55vh;
    }
    .contact-form{
        display: grid;
        grid-template-columns: 50% 50%;
        row-gap: 10px;
        column-gap: 10px;
    }
    .container-w900{
        max-width: 900px;
        margin-left: auto;
        margin-right: auto;
        padding: 50px 0;
    }
    @media(max-width: 1000px){
        .container-w900{
            max-width: unset;
            margin: unset;
            padding: 50px;
            width: 100%;
        }
    }
    .input{
        padding: 8px 14px;
        font-size: 2rem;
        outline: 0;
    }
    textarea{
        grid-column: 1 / span 2;
        resize: vertical;
    }
    @media(max-width: 768px){
        .contact{
            height: fit-content;
        }
        textarea{
            grid-column: unset;
        }
        .contact-form{
            grid-template-columns: 100%;
            column-gap: unset;
        }
    }
    @media(max-width: 668px){
        .input{
            padding: 8px 14px;
            font-size: 1.6rem;
            outline: 0;
        }
        .contact-btn{
            font-size: 1.8rem !important;
        }
    }
</style>