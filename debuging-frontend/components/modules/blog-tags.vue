<template>
    <div class="blog-tag-component">
        <a target="_blank" :href="`${url}`">{{ title }}</a>
    </div>
</template>

<script>
export default {
    props:{
        url:{
            type: String,
            default: () => ''
        },
        title:{
            type: String,
            default: () => ''
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.blog-tag-component {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 6px 16px;
    border: 1px solid $primary;
    background-color: $white;
    border-radius: 5px;
    a {
        font-family: 'Poppins';
        font-style: normal;
        font-weight: 300;
        font-size: 16px;
        color: $black;
        text-decoration: none;
    }
    &:hover {
        background-color: $green-100;
    }
}
</style>