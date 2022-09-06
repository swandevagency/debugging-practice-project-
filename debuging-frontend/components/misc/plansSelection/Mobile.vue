<template>
    <div class="plan-container">
        <select name="plans" class="plan-container-options">
            <option value="e-commerce">e-commerce</option>
            <option value="Portfolio">Portfolio</option>
            <option value="Service">Service</option>
            <option value="e-commerce">e-commerce</option>
            <option value="Test-site">Test-site</option>
        </select>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.plan-container{
    width: 100%;
    
    @include mq(lg) {
        display: none;
    }
}
.plan-container-options{
    border: $primary 1px solid;
    width: 100%;
    font-family: inherit;
    font-size: inherit;
    cursor: pointer;
    border-radius: 10px;
    padding: 18px 17px;
    margin: 45px 0px 30px;
    outline: none;
    background: #fff;
}
</style>