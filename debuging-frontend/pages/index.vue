<template>
  <div class="home-page-wrapper">
    <section class="home-page-landing-section-wrapper container">
      <LandingSectionItem
        :title="landingSection.title"
        :description="landingSection.description"
        :button="true"
        buttonText="Get a quick quote"
      >
        <img src="/image/home-page/landing.png" alt="landing photo" />
      </LandingSectionItem>
    </section>
    <section class="home-page-what-we-do-section-wrapper">
      <div class="section-top-svg">
        <BackgroundTop />
      </div>
      <div class="section-bottom-svg">
        <BackgroundBottom />
      </div>
      <WhatWeDo />
    </section>
    <section class="home-page-about-webclicks-section-wrapper container">
      <AboutWebClicks />
    </section>
    <section class="home-page-plans-section-wrapper">
      <div class="section-top-svg">
        <BackgroundTop />
      </div>
      <div class="section-bottom-svg">
        <BackgroundBottom />
      </div>
      <PlansSection />
    </section>
    <section class="home-page-blogs-section-wrapper container">
      <BlogsSection />
    </section>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      landingSection: {
        title: 'Dont Consider Limitation',
        description:
          'We help businesses take off and scale up quickly with perfectly crafted and effective web experiences.',
      },
    }
  },
  components: {
    WhatWeDo: () =>
      import('@/components/sections/homepage/what-we-do/index.vue'),
    PlansSection: () =>
      import('@/components/sections/homepage/plans/index.vue'),
    LandingSectionItem: () =>
      import('@/components/modules/landing-section-item.vue'),
    HomePageLanding: () => import('@/components/icons/home-page-landing.vue'),
    AboutWebClicks: () =>
      import('@/components/sections/homepage/about-webClicks/index.vue'),
    BlogsSection: () =>
      import('@/components/sections/homepage/blogs/index.vue'),
    BackgroundTop: () => import('@/components/icons/background/top.vue'),
    BackgroundBottom: () => import('@/components/icons/background/bottom.vue'),
  },
})
</script>
<style lang="scss" scoped>
//todo fix the svg on top of the 2 sections
//todo fix the h5 h2 p classes
@import '@/assets/scss/global.scss';
.home-page-what-we-do-section-wrapper {
  margin-top: 85px;
  background-color: $green-50;
  padding: 40px 0px;
  position: relative;
}
.section-top-svg {
  position: absolute;
  top: -9vw;
  width: 100%;
  svg {
    width: 100%;
    height: 100%;
  }
}
.section-bottom-svg {
  position: absolute;
  top: 100%;
  width: 100%;
  svg {
    width: 100%;
    height: 100%;
  }
}
.home-page-plans-section-wrapper {
  margin-top: 100px;
  background-color: $green-50;
  padding: 40px 0px;
  position: relative;
}
.home-page-about-webclicks-section-wrapper {
  margin-top: 100px;
}
.home-page-blogs-section-wrapper {
  margin-top: 100px;
  margin-bottom: 100px;
  @include mq(lg) {
    margin-top: 250px;
    margin-bottom: 250px;
  }
}
@include mq(lg) {
  .home-page-what-we-do-section-wrapper {
    margin-top: 180px;
  }
  .home-page-about-webclicks-section-wrapper {
    margin-top: 180px;
  }
}
@include mq(xl) {
  .home-page-what-we-do-section-wrapper {
    margin-top: 300px;
  }
  .home-page-about-webclicks-section-wrapper {
    margin-top: 300px;
  }
  .home-page-plans-section-wrapper {
    margin-top: 300px;
  }
}
</style>
