<template>
        <div class="development-languages-wrapper">
            <div class="development-languages-items">
                <div>
                    <img :src="`/image/carousel-icons/${icon}.png`" :alt="`${title}`" />
                </div>
                <p>{{ title }}</p>
            </div>
        </div>
</template>

<script>
export default {
    props: {
        icon:{
            type : String,
            default : () => ''
        },
        title:{
            type: String,
            default: () => 'write the title of advantages',
        },
    },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.development-languages-items{
    color: #b1b1b1;
    display: flex;
    flex-direction: column;
    align-items: center;
}

</style>