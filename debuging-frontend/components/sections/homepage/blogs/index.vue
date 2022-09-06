<template>
  <div class="blog-section-container">
    <div class="blogs-preview-information-wrapper">
      <h5 class="blogs-preview-sub-title">articles</h5>
      <h2 class="blogs-preview-title">Stay up to date with the latest news</h2>
      <div class="blogs-preview-items-wrapper">
        <BlogItem
          v-for="blog in blogsPreview"
          :key="blog.id"
          :blogData="blog"
        />
      </div>
    </div>
    <div class="blogs-articles-categories-wrapper">
      <h4 class="blogs-articles-title">Discover articles in other category</h4>
      <div class="blogs-article-container">
        <CategoryItem
          class="category-article"
          v-for="blogCategory in blogCategories"
          :key="blogCategory.id"
          :categoryData="blogCategory"
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  components: {
    BlogItem: () => import('@/components/modules/blog-item.vue'),
    CategoryItem: () => import('@/components/modules/categoryItem.vue'),
  },
  data() {
    return {
      blogsPreview: [
        {
          id: '285802985',
          title:
            'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
          description:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
          imageUrl: '/imgs/blog-test1.jpg',
          writer: {
            name: 'Shayan Azali',
            imageUrl: '/imgs/testProfile.jpg',
          },
          publishedAt: 'aug 7',
          timeToRead: '7',
        },
        {
          id: '285802934534685',
          title:
            'The art of collaboration: land your dream client with workspace',
          description:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
          imageUrl: '/imgs/blog-test2.jpg',
          writer: {
            name: 'Shayan Azali',
            imageUrl: '/imgs/testProfile.jpg',
          },
          publishedAt: 'aug 7',
          timeToRead: '7',
        },
        {
          id: '285802768678985',
          title: 'Dilemma between using CMS or native website',
          description:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
          imageUrl: '/imgs/blog-test3.jpg',
          writer: {
            name: 'Shayan Azali',
            imageUrl: '/imgs/testProfile.jpg',
          },
          publishedAt: 'aug 7',
          timeToRead: '7',
        },
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
          id: '234234',
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
})
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.blog-section-container {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
  @include mq(lg) {
    align-items: flex-start;
    justify-content: space-between;
  }
}
.blogs-preview-information-wrapper {
  @include mq(lg) {
    flex-basis: 50%;
  }
}
.blogs-preview-sub-title {
  color: $subTitle-color;
  font-size: 14px;
  text-transform: uppercase;
  font-weight: 500;
  //todo need to fix the font family
  @include mq(lg) {
    font-size: 16px;
  }
}
.blogs-preview-title {
  margin-top: 8px;
  @include mq(lg) {
    margin-bottom: 90px;
  }
}
.blogs-preview-items-wrapper {
  margin-top: 57px;
}
.blogs-articles-categories-wrapper {
  display: none;
  @include mq(lg) {
    flex-basis: 40%;
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    flex-direction: column;
    position: sticky;
    top: 20px;
    margin-top: 35px;
  }

  .blogs-articles-title {
    margin-bottom: 35px;
  }
  .blogs-article-container {
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    flex-wrap: wrap;
    gap: 20px;
    grid-gap: 20px;
  }
}
</style>
