<template>
    <div class="promoted-blog-item">
        <p class="promoted-blog-description">
            {{ description }}
        </p>
        <div class="promoted-blog-image">
            <img :src="`/image/promoted-blog/${picture}.png`" :alt="`${picture}`" />
        </div>
    </div>
</template>

<script>
export default {
    props: {
        // write the title of member
        description: {
            type: String,
            default: () => 'You need to write blog description',
        },
        // write the image url
        picture: {
            type: String,
            default: () => 'image url',
        },
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.promoted-blog-item{
    margin-top: 30px;
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}

.promoted-blog-description{
    flex-basis: 76%;
    color: $title-color;
    font-size: 18px;
    font-weight: 500;
}

.promoted-blog-image{
    flex-basis: 22%;

    img{
        width: 100%;
    }
}
</style>