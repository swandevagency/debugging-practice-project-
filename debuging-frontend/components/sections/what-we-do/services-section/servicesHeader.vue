<template>
    <div>
        <div class="services-section-header">
            <h2>Services we can help you with</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Eget nunc scelerisque viverra mauris in aliquam sem fringilla.</p>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.services-section-header{
    width: 100%;
    display: flex;
    flex-direction: column; 
    align-items: flex-start;  
    
    p{
        margin: 30px 0px 50px;
        @include mq(lg){
            margin: 35px 0px 80px;
            line-height: 33px;
        }
    }
}

</style>