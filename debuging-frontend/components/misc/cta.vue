<template>
  <div class="call-to-action-wrapper">
    <div class="call-to-action">
      <div class="call-to-action-container">
        <h2>Have a project in mind ?</h2>
        <p>
          Laboris anim laboris ex deserunt incididunt quis nostrud ipsum esse eu
          nisi.
        </p>
        <div>
          <CtaButton buttonType="secondary" :buttonText="button.buttonText" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      button: {
        buttonText: 'Get a quick quote',
      },
    }
  },
  components: {
    CtaButton: () => import('@/components/modules/button-item.vue'),
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.call-to-action-wrapper {
  width: 100%;
  display: flex;
  justify-content: center;
}

.call-to-action {
  width: 100%;
  @include mq(lg) {
      width: 55%;
  }
  background-color: $bg-dark;
  border-radius: 10px;
}

.call-to-action-container {
  width: 100%;
  padding: 40px;
  display: flex;
  flex-direction: column;
  align-items: center;

  h2 {
    color: $secondary;
    text-align: center;
    text-transform: uppercase;
  }

  p {
    color: $secondary-light;
    text-align: center;
    text-transform: uppercase;
    margin: 40px 0px;
  }
}
</style>
