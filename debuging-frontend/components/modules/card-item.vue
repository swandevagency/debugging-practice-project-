<template>

    <div :class="['card', pattern ?  'pattern' : '', utilityClass ? utilityClass : '']">
        <slot />
    </div>

</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    props: {
        pattern: {
            type: Boolean,
            default: () => false,
        },
        utilityClass: {
            type: String,
        }
    }
})
</script>

<style lang="scss">
@import '@/assets/scss/global.scss';

.card {
    position: relative;
    padding: 10px 20px;
    border: 1px solid $primary;
    border-radius: 10px;
    background-color: $white;


    &::before {
        content: '';
        position: absolute;
        background: url('/icons/Dots.svg') no-repeat;
        width: 90px;
        height: 150px;
        top: -10px;
        left: -10px;
        z-index: -1; 
        
        @include mq(lg) {
            width: 110px;
            height: 200px;
            top: -30px;
            left: -20px;
        }
    }
}

.pattern{
    background: url('@/static/icons/pattern.svg');
    position: absolute;
    top: -25px;
    left: -30px;
    width: 111px;
    height: 200px;
}
</style>