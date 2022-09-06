<template>
    <div>
        <div class="card-item-wrapper">
            <div>
                <div v-html="icon"></div>
                <h3>{{ title }}</h3>
            </div>
            <p>{{ content }}</p>
            <h6>min price: {{ price }}T</h6>
            <div class="card-contact-us-button">
                <CardButtons :buttonText="button.buttonText"/>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            button:{
                buttonText:'Contact us',
            }    
        }
    },
    props: {
        icon: {
            type: String,
            default: () => ''
        },
        title: {
            type: String,
            default: () => 'need to write something here'
        },
        content: {
            type: String,
            default: () => 'need to write something here'
        },
        price: {
            type: String,
            default: () => '0000'
        }
    },
    components:{
        CardButtons:() => import ('@/components/modules/button-item.vue')
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.card-item-wrapper{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px 10px;

    p{
        text-align: center;
        margin: 25px 0px;
    }

    &>div:first-child{
        display: flex;
        flex-direction: row;
        align-items: center;

        h3{
            margin-left: 10px;
        }
    }

    .card-contact-us-button{
        margin: 30px 0px 0px;
    }
}


</style>
