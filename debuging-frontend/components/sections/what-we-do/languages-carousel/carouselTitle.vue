<template>
    <div class="development-carousel-title">
        <h2>languages that we use for <br /> {{ title }}</h2>  
    </div>
</template>

<script>
export default {
    props:{
        title:{
            type : String,
            default : () => ''
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.development-carousel-title{
    margin-top: 100px;
    margin-bottom: 70px;
}
</style>