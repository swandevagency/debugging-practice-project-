<template>
    <div>
        <div class="project-offer-section">
            <h2>Proident officia tempor reprehenderit</h2>
            
            <p>Amet ad ullamco commodo ad fugiat eiusmod qui officia irure mollit cillum non ipsum. Magna id duis voluptate nulla aute sit nostrud voluptate labore exercitation ullamco duis. Eu eiusmod ipsum exercitation ad enim ullamco veniam cupidatat nisi pariatur amet. Deserunt quis nulla elit ut eiusmod sint. Aliquip ullamco ad proident. Labore consequat reprehenderit magna esse officia commodo quis nisi dolore nostrud.</p>
            
            <CallToAction />
        </div>
    </div>
</template>

<script>
export default {
    components:{
        CallToAction: () => import('@/components/misc/cta'),
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.project-offer-section{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    
    p{
        margin: 30px 0px 50px;

        @include mq(lg){
            line-height: 33px;
        }
    }

    div{
        margin-top: 80px;
        margin-bottom: 130px;
    
        @include mq(lg){
            margin-top: 120px;
            margin-bottom: 150px;
        }
    }
}
</style>