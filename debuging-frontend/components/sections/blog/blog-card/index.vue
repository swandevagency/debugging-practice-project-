<template>
    <div class="promoted-section-wrapper">
        <CardItem>
            <div class="promoted-blog-wrapper">
                <PromotedTitle />
                <div v-for="promoted in promoteds" :key="promoted.id">
                    <PromotedBlog :description="promoted.description" :picture="promoted.picture" />    
                </div>
            </div>
            <div class="blogs-tags-categories-wrapper">
                <h4 class="Tags-title">Tags:</h4>
                <div class="tags-container">
                    <TagItem
                        class="category-article"
                        v-for="blogCategory in blogCategories"
                        :key="blogCategory.id"
                        :categoryData="blogCategory"
                    />
                </div>
            </div>
        </CardItem>
    </div>
</template>

<script>
export default {
    components:{
        CardItem: () => import("@/components/modules/card-item.vue"),
        PromotedBlog: () => import("@/components/sections/blog/promoted-blog/index.vue"),
        TagItem: () => import("@/components/modules/categoryItem.vue"),
        PromotedTitle: () => import("@/components/sections/blog/promoted-blog/promotedTitle.vue"),
    },
    data() {
        return {
            promoteds:[
                {
                    description: "Color and psychological functioning: a review of theoretical ...",
                    picture: 'pexels-zaksheuskaya'
                },
                {
                    description: "The art of collaboration: land your dream client with workspace",
                    picture: "pexels-zaksheuskaya-2"
                },
                {
                    description: "Dilemma between using CMS or native website",
                    picture: "pexels-zaksheuskaya-3"
                }
            ],
            blogCategories: [
                {
                    name: 'test1',
                    id: '1',
                },
                {
                    name: 'test2',
                    id: '2',
                },
                {
                    name: 'tedsfsdfst3',
                    id: '3',
                },
                {
                    name: 'test4',
                    id: '4',
                },
                {
                    name: 'test4',
                    id: '4',
                },
                {
                    name: 'test6',
                    id: '6234234',
                },
                {
                    name: 'test1dasf',
                    id: '12342533',
                },
                {
                    name: 'testhsdfsh1',
                    id: '1235464',
                },
                {
                    name: 'test1fdsg',
                    id: '154654623',
                },
                {
                    name: 'test109898234',
                    id: '109182',
                },
            ],
        }
    },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.blogs-tags-categories-wrapper{
    margin-top: 40px;
}

.tags-title {
    margin-bottom: 35px;
}

.tags-container {
    margin-top: 30px;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    justify-content: flex-start;
    div{
        margin-bottom: 20px;
        margin-right: 20px;
    }
}

.promoted-blog-wrapper{
    display: none;

    @include mq(lg){
        display: initial;
    }
}


</style>