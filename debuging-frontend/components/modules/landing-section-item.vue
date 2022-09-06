<template>
  <div class="landing-section-component-wrapper">
    <div class="landing-section-description-wrapper">
      <h1 class="landing-section-title">{{ title }}</h1>
      <p class="landing-section-description">{{ description }}</p>
      <div class="landing-section-button-wrapper" v-if="button">
        <ButtonItem :buttonText="buttonText" />
      </div>
    </div>
    <div class="landing-section-svg-container">
      <!-- //* this is where the svg get imported -->
      <slot />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    //* write the title for the landing section
    title: {
      type: String,
      default: () => 'You need to write something in here',
    },
    //* write the description for the landing section
    description: {
      type: String,
      default: () =>
        'Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium, sint porro totam in eum assumenda iusto impedit qui. Possimus, quasi. Nulla, laboriosam quisquam. Minima sed adipisci ut doloremque pariatur similique.',
    },
    //! if true the button will be shown
    button: {
      type: Boolean,
      default: () => false,
    },
    buttonText: {
      type: String,
      default: () => '',
    },
  },
  components: {
    ButtonItem: () => import('@/components/modules/button-item.vue'),
  },
})
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.landing-section-component-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.landing-section-description-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .landing-section-title {
    font-size: 36px;
    text-align: center;
    line-height: 54px;
  }
  .landing-section-description {
    text-align: center;
    font-size: 18px;
    line-height: 27px;
    margin-top: 25px;
  }
  .landing-section-button-wrapper {
    margin-top: 20px;
  }
}
.landing-section-svg-container {
  width: 90%;
  margin-top: 50px;
  svg {
    width: 100%;
    height: 100%;
  }
}
@include mq(sm) {
  .landing-section-svg-container {
    width: 80%;
  }
}
@include mq(md) {
  .landing-section-svg-container {
    width: 70%;
  }
}
@include mq(lg) {
  .landing-section-component-wrapper {
    flex-direction: row;
  }
  .landing-section-description-wrapper {
    flex-basis: calc(100% / 2 - 20px);
    .landing-section-title {
      text-align: left;
      line-height: 60px;
      width: 100%;
    }
    .landing-section-description {
      text-align: left;
      margin-top: 50px;
      width: 100%;
      line-height: 32px;
    }
    .landing-section-button-wrapper {
      align-self: flex-start;
      margin-top: 40px;
    }
  }
  .landing-section-svg-container {
    flex-basis: calc(100% / 2 - 20px);
  }
}
@include mq(xl) {
  .landing-section-description-wrapper {
    .landing-section-title {
      line-height: 96px;
      font-size: 64px;
    }
    .landing-section-description {
      line-height: 45px;
      font-size: 24px;
    }
  }
}
</style>
