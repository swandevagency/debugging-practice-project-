<template>
    <div class="plan-container">
        <form class="plan-container-options" action="#">
            <p>
                <input type="radio" id="plan1" name="plan-selection" checked>
                <label @click="getCoordinate1()" for="plan1" ref="plan1">
                    e-commerce
                </label>
            </p>
            <p>
                <input type="radio" id="plan2" name="plan-selection">
                <label @click="getCoordinate2()" for="plan2" ref="plan2">
                    Portfolio
                </label>
            </p>
            <p>
                <input type="radio" id="plan3" name="plan-selection">
                <label @click="getCoordinate3()" for="plan3" ref="plan3">
                    Service
                </label>
            </p>
            <p>
                <input type="radio" id="plan4" name="plan-selection">
                <label @click="getCoordinate4()" for="plan4" ref="plan4">
                    e-commerce
                </label>
            </p>
            <p>
                <input type="radio" id="plan5" name="plan-selection">
                <label @click="getCoordinate5()" for="plan5" ref="plan5">
                    Test-site
                </label>
            </p>
            
            <div class="animation-rectangle"  ref="rectangle"></div>

        </form>
    </div>
</template>

<script>
export default {
    mounted() {
        let plan = this.$refs.plan1;
        let rectangle = this.$refs.rectangle;
        const width = plan.offsetWidth;
        rectangle.style.width = width + 'px'
    },
    methods:{
        getCoordinate1() {
            let plan = this.$refs.plan1;
            let rectangle = this.$refs.rectangle;
            rectangle.style.left = plan.offsetLeft + 'px';
            rectangle.style.animation = 'bounce' + '0.5s' + 'linear';
            const width = plan.offsetWidth;
            rectangle.style.width = width + 'px'

        },
        getCoordinate2() {
            let plan = this.$refs.plan2;
            let rectangle = this.$refs.rectangle;
            rectangle.style.left = plan.offsetLeft + 'px';
            rectangle.style.animation = 'bounce 0.5s linear';
            const width = plan.offsetWidth 
            rectangle.style.width = width + 'px'
            
        },
        getCoordinate3() {
            let plan = this.$refs.plan3;
            let rectangle = this.$refs.rectangle;
            rectangle.style.left = plan.offsetLeft + 'px';
            const width = plan.offsetWidth;
            rectangle.style.width = width + 'px'

        },
        getCoordinate4() {
            let plan = this.$refs.plan4;
            let rectangle = this.$refs.rectangle;
            rectangle.style.left = plan.offsetLeft + 'px';
            const width = plan.offsetWidth;
            rectangle.style.width = width + 'px'

        },
        getCoordinate5() {
            let plan = this.$refs.plan5;
            let rectangle = this.$refs.rectangle;
            rectangle.style.left = plan.offsetLeft + 'px';
            const width = plan.offsetWidth;
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
.plan-container-options{
    position: relative;
    background: $bg-secondary;
    border-radius: 50px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 85%;
    padding: 17px 5px;
    margin: 50px 0px;

    p{
        z-index: 5;
    }

    label{
        cursor: pointer;
        position: relative;
        z-index: 5;
        padding: 0px 15px;
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
    transition: all 0.2s ease;
}

@keyframes bounce { 
    0% { transform: translateX(0); } 
    50% { transform: translateX(4px); } 
    100% { transform: translateX(0px); } 
}
</style>