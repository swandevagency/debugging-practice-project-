<template>
    <div class="advantage-items-container">
        <div class="advantage-item-description">
            <h4>{{ title }}</h4>
            <p>{{ description }}</p>
        </div>
        <div class="advantage-item-image">
            <img :src="`/image/what-we-do-page/${image}.png`" :alt="`${title}`" />
        </div>
    </div>
</template>

<script>
export default {
    props:{
        advantages:{
            type: Array,
            default: () => []
        },
        title:{
            type: String,
            default: () => 'write the title of advantages',
        },
        description:{
            type: String,
            default: () => 'Write the description of advantages',    
        },
        image:{
            type: String,
            default: () => 'images url',
        } 
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.advantage-items-container{
    display: flex;
    flex-direction: column;
    margin-bottom: 100px;

    @include mq(lg){
        justify-content: space-between;
        align-items: center;
        flex-direction: row-reverse;
        
        &:nth-child(even){
            flex-direction: row;
        }
    }
    
}

.advantage-item-description{
    p{
        margin-top: 20px;
        margin-bottom: 30px;
    }

    @include mq(lg){
        flex-basis: 58%;
    }
}

.advantage-item-image{
    align-self: center;

    @include mq(lg) {
        flex-basis: 33%;
    }

    img{
        width: 100%;
        
        @include mq(md){
            max-width: 510px;
        } 
    }
}

</style>