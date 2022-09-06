<template>
    <div>
        <div class="services-section-container">
            <div>
                <div class="services-section-title-icon" v-html="icon"></div>
                <h4>{{ title }}</h4>
            </div>
            <p>{{ content }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        icon:{
            type: String,
            default: () => ''
        },
        title:{
            type: String,
            default: () => 'services card title'
        },
        content:{
            type: String,
            default: () => 'services card content'
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.services-section-container{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 0px 10px;
    
    p{
        text-align: center;
        margin: 25px 0px;
    }

    @include mq(lg){
        align-items: flex-start;

        p{
            text-align: left;
        }
    }

    &>div:first-child{
        display: flex;
        flex-direction: column;
        align-items: center;

        @include mq(lg){
            flex-direction: row;
        }

        h4{
            margin-left: 10px;
        }
    }
}

.services-section-title-icon{
    margin-right: 30px;
}

</style>