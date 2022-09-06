<template>
  <div class="what-we-do-section-container container">
    <div class="what-we-do-intro-wrapper">
      <div class="what-we-do-info-wrapper">
        <h5>what we do</h5>
        <h2>pulvinar neque laoreet suspendisse</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Eget nunc
          scelerisque viverra mauris in aliquam sem fringilla.
        </p>
      </div>
      <div class="what-we-do-info-svg-wrapper">
        <img src="/image/home-page/what-we-do.png" alt="what we do picture" />
      </div>
    </div>
    <div class="what-we-do-items-wrapper">
      <div class="what-we-do-item-container">
        <div class="item-svg">
          <BackendDevSvg />
        </div>
        <div class="item-info">
          <h5 class="item-title">Backend Development</h5>
          <p class="item-description">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et
          </p>
        </div>
      </div>
      <div class="what-we-do-item-container">
        <div class="item-svg">
          <UiUxDesignSvg />
        </div>
        <div class="item-info">
          <h5 class="item-title">UI/UX</h5>
          <p class="item-description">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et
          </p>
        </div>
      </div>
      <div class="what-we-do-item-container">
        <div class="item-svg">
          <FrontendDevSvg />
        </div>
        <div class="item-info">
          <h5 class="item-title">Frontend Development</h5>
          <p class="item-description">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et
          </p>
        </div>
      </div>
      <div class="what-we-do-item-container">
        <div class="item-svg pwa">
          <PWASvg />
        </div>
        <div class="item-info">
          <h5 class="item-title">Progressive Web App</h5>
          <p class="item-description">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et
          </p>
        </div>
      </div>
    </div>
    <div class="what-we-do-button-container">
      <ButtonItem buttonText="Read more about our work" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  components: {
    UiUxDesignSvg: () => import('@/components/icons/uiUxDesign-svg.vue'),
    FrontendDevSvg: () => import('@/components/icons/frontendDev-svg.vue'),
    PWASvg: () => import('@/components/icons/PWA-svg.vue'),
    BackendDevSvg: () => import('@/components/icons/backendDev-svg.vue'),
    WhatWeDoSvg: () => import('@/components/icons/what-we-do-section.vue'),
    ButtonItem: () => import('@/components/modules/button-item.vue'),
  },
})
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.what-we-do-section-container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.what-we-do-info-wrapper {
  h5 {
    color: $subTitle-color;
    font-size: 14px;
    font-weight: 500;
    text-transform: uppercase;
    //todo need to fix the font family
    // font-family: 'Space Grotesk';
  }
  h2 {
    margin-bottom: 30px;
    margin-top: 8px;
  }
}
.what-we-do-info-svg-wrapper {
  display: none;
}
.what-we-do-items-wrapper {
  display: flex;
  flex-wrap: wrap;
  align-items: flex-start;
  justify-content: space-between;
  margin-top: 40px;
}
.what-we-do-item-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  flex-basis: calc(100% / 2 - 10px);
  margin-bottom: 40px;
  .item-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    .item-description {
      display: none;
      text-align: center;
    }
    .item-title {
      text-align: center;
      font-size: 16px;
      margin-top: 20px;
    }
  }
}
@include mq(lg) {
  .what-we-do-info-wrapper {
    p {
      line-height: 33px;
    }
  }
  .what-we-do-info-svg-wrapper {
    position: relative;
    display: initial;
    width: 100%;
    bottom: 150px;
  }
  .what-we-do-intro-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .what-we-do-items-wrapper {
    width: 90%;
    margin-bottom: 80px;
  }
  .what-we-do-item-container {
    flex-basis: calc(100% / 4 - 20px);
    margin-bottom: 0px;
    .item-svg {
      width: 60px;
      height: 60px;
      svg {
        width: 100%;
        height: 100%;
      }
    }
    .pwa {
      width: 70px;
    }
    .item-info {
      .item-title {
        font-size: 16px;
        min-height: 60px;
      }
      .item-description {
        font-size: 16px;
        display: inline;
        line-height: 27px;
      }
    }
  }
}
@include mq(xl) {
  .what-we-do-intro-wrapper {
    justify-content: space-between;
  }
  .what-we-do-info-wrapper {
    flex-basis: 45%;
  }
  .what-we-do-info-svg-wrapper {
    flex-basis: 45%;
    bottom: 200px;
  }
  .what-we-do-items-wrapper {
    margin-bottom: 100px;
  }
  .what-we-do-item-container {
    flex-basis: calc(100% / 4 - 30px);
    .item-svg {
      width: 100px;
      height: 100px;
    }
    .pwa {
      width: 120px;
    }
    .item-info {
      .item-title {
        font-size: 18px;
      }
      .item-description {
        font-size: 18px;
      }
    }
  }
}
</style>
