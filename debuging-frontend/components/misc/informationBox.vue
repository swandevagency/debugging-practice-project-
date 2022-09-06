<template>
    <div>
        <div class="information-box-wrapper">
            <div class="information-box-container">
                <p>{{ description }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        description:{
            type: String,
            default: ()=> 'you need to write info in here'
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.information-box-wrapper{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.information-box-container{
    width: 100%;
    padding: 30px 30px;
    border-radius: 10px;
    background-color: $aqua-100;
    
    p{
        font-weight: 400;
        font-size: 20px;
        line-height: 45px;
        color: $title-color;
        letter-spacing: 0.02em;
    }
    
    @include mq(lg){
        padding: 30px 95px;
        width: 75%;
        p{
            text-align: center;
        }
    }
}
</style>