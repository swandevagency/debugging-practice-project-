<template>
    <div>
        <div class="plans-selecting-section-wrapper">
            <div class="plans-selecting-section">
                <h2>
                    Reprehenderit ad quis elit veniam
                </h2>

                <div>
                    <PlansSelectionMobile />
                    <PlansSelectionDesktop />
                </div>

                <p>
                    Aliquip ex proident magna velit. Lorem ipsum culpa ex ullamco incididunt ex reprehenderit sunt cillum cillum exercitation ex consectetur magna est. Culpa qui officia do ut sit exercitation. Cupidatat occaecat pariatur ea commodo enim nulla culpa ea ut occaecat amet dolor aliqua dolor mollit. Ex commodo nulla cupidatat esse dolore aute quis. Aliqua aute Lorem fugiat incididunt tempor occaecat.
                </p>    
            </div>
        </div>
    </div>
</template>

<script>
export default {
    components: {
        PlansSelectionMobile: () => import ('~/components/misc/plansSelection/Mobile.vue'),
        PlansSelectionDesktop: () => import ('~/components/misc/plansSelection/Desktop.vue'),
        
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.plans-selecting-section-wrapper{
    width: 100%;
    display: flex;
    align-items: center;
    margin-top: 170px;
    margin-bottom: 90px;
}

.plans-selecting-section{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    &>div{
        width: 100%;
        align-self: center;
        @include mq(lg) {
            width: 70%;
        }
    }

    h2{
        text-transform: uppercase;
    }

    p{
        font-weight: 300;
    }
}
</style>