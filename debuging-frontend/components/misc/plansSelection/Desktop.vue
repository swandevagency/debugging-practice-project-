<template>
    <div class="plan-container">
        <form class="plan-container-form" action="#">
                <input type="radio" id="plan1" name="plan-selection" checked>
                <p @click="getCoordinate" for="plan1" ref="firstPlan">
                    e-commerce
                </p>

                <input type="radio" id="plan2" name="plan-selection">
                <p @click="getCoordinate" for="plan2">
                    Portfolio
                </p>

                <input type="radio" id="plan3" name="plan-selection">
                <p @click="getCoordinate" for="plan3">
                    Service
                </p>

                <input type="radio" id="plan4" name="plan-selection">
                <p @click="getCoordinate" for="plan4">
                    e-commerce
                </p>

                <input type="radio" id="plan5" name="plan-selection">
                <p @click="getCoordinate" for="plan5">
                    Test-site
                </p>
            <div class="animation-rectangle"  ref="rectangle"></div>
        </form>
    </div>
</template>

<script>
export default {
    mounted() {
        let rectangle = this.$refs.rectangle;
        // defining rectangle width at frist
        const width = this.$refs.firstPlan.offsetWidth;
        rectangle.style.width = width + 'px'
    },
    methods:{
        getCoordinate(e) {
            let rectangle = this.$refs.rectangle;
            // position the rectangle by the position of element
            rectangle.style.left = e.target.offsetLeft + 'px';
            // defining the rectangle width by text width + padding
            const width = e.target.offsetWidth;
            rectangle.style.width = width + 'px'
        },
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.plan-container{
    width: 100%;
    display: none;
    @include mq(lg) {
        display: initial;
        display: flex;
        align-items: center;
        justify-content: center;
    }
}
.plan-container-form{
    position: relative;
    background: $bg-secondary;
    border-radius: 50px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 85%;
    padding: 0px 5px;
    margin: 50px 0px;
    
    p{
        z-index: 5;
        cursor: pointer;
        position: relative;
        z-index: 5;
        padding: 0px 15px;
        height: 65px;
        display: flex;
        align-items: center;
        user-select: none;
    }

    input{
        display: none;
    }
}

.animation-rectangle{
    position: absolute;
    width: 100px;
    height: 90%;
    background-color: #fff;
    border-radius: 50px;
    box-shadow: 11px 7px 5px rgba(22, 68, 45, 0.01), 6px 4px 4px rgba(22, 68, 45, 0.02), 3px 2px 3px rgba(22, 68, 45, 0.04), 1px 0px 2px rgba(22, 68, 45, 0.04), 0px 0px 0px rgba(22, 68, 45, 0.04);
    transition: all 0.2s cubic-bezier(.08,1,.88,1.16);
}

</style>