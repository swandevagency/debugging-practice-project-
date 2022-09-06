<template>
  <div class="blog-item-wrapper" v-if="blogData">
    <div class="blog-image-container">
      <img
        v-if="blogData.imageUrl"
        :src="blogData.imageUrl"
        :alt="blogData.title"
      />
    </div>
    <div class="blog-info-wrapper">
      <h6 class="blog-title">
        {{ trimText(blogData.title, 65) }}
      </h6>
      <p class="blog-description">
        {{ trimText(blogData.description, 65) }}
      </p>
      <div class="blog-writer-container" v-if="blogData.writer">
        <div class="blog-writer-image">
          <img
            v-if="blogData.writer.imageUrl"
            :src="blogData.writer.imageUrl"
            :alt="blogData.writer.name"
          />
        </div>
        <p class="writer-name" v-if="blogData.writer.name">
          {{ blogData.writer.name }} -
        </p>
        <p class="published-at" v-if="blogData.publishedAt">
          {{ blogData.publishedAt }} -
        </p>
        <p class="time-to-read" v-if="blogData.timeToRead">
          {{ blogData.timeToRead }} min
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: ['blogData'],
  methods: {
    trimText(text: string, length: number) {
      if (text.length > length) {
        const newText = text.substring(0, length)
        const textArray = newText.split(' ')
        textArray.pop()
        const result = textArray.join(' ') + '...'
        return result
      } else {
        return text
      }
    },
  },
})
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.blog-item-wrapper {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  position: relative;
  margin-top: 50px;
  cursor: pointer;
  .blog-image-container {
    border-radius: 10px;
    width: 100px;
    height: 100px;
    position: relative;
    overflow: hidden;
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    &::after {
      position: absolute;
      content: '';
      width: 200%;
      height: 200%;
      top: -50px;
      left: -50px;
      border-radius: 50%;
      transition: all linear 0.35s;
      background-color: rgba(0, 0, 0, 0.2);
    }
    @include mq(lg) {
      width: 145px;
      height: 145px;
    }
  }
  &:hover {
    .blog-image-container {
      &::after {
        width: 30px;
        height: 30px;
        border-radius: 50%;
        top: 100%;
        left: 100%;
      }
    }
  }
  &::before {
    content: '';
    position: absolute;
    background: url('/icons/Dots.svg') no-repeat;
    width: 100px;
    height: 100px;
    top: -20px;
    left: -20px;
    z-index: -1;
    @include mq(lg) {
      width: 145px;
      height: 145px;
      top: -30px;
      left: -40px;
    }
  }
}
.blog-info-wrapper {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  flex-direction: column;
  height: 100px;
  flex-basis: 65%;
  .blog-description {
    display: none;
    @include mq(xl) {
      display: inline;
      font-size: 16px;
      margin-bottom: 13px;
      line-height: 20px;
    }
  }
  .blog-title {
    margin-bottom: 8px;
    line-height: 24px;
    @include mq(xl) {
      line-height: 27px;
      margin-bottom: 13px;
    }
  }
  .blog-writer-container {
    display: flex;
    align-items: center;
    justify-content: center;
    .blog-writer-image {
      width: 30px;
      height: 30px;
      border-radius: 50%;
      img {
        object-fit: cover;
        border-radius: 50%;
        width: 100%;
        height: 100%;
      }
    }
    p {
      margin-left: 5px;
      color: #b1b1b1;
      font-size: 10px;
    }
  }
  @include mq(sm) {
    flex-basis: 75%;
  }
  @include mq(md) {
    flex-basis: 80%;
  }
  @include mq(lg) {
    flex-basis: 65%;
    height: 145px;
  }
  @include mq(xl) {
    flex-basis: 70%;
  }
  @include mq(xxl) {
    flex-basis: 75%;
  }
}
</style>
