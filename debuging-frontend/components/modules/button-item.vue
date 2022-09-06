<template>
  <button
    :class="[
      buttonType == 'secondary'
        ? 'button-item-container-secondary'
        : buttonType == 'select'
        ? 'button-item-container-select'
        : 'button-item-container',
    ]"
  >
    <span>{{ buttonText }}</span>
  </button>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    buttonText: {
      type: String,
      default: () => 'you need to write the text',
    },
    //* default is background color white- secondary type is for the button with background of linear gradients- select type is for submit button for form
    buttonType: {
      type: String,
      default: () => '',
    },
  },
})
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.button-item-container {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 20px;
  border-radius: 50px;
  border: 1px solid $primary;
  background-color: $white;
  cursor: pointer;
  position: relative;
  span {
    position: relative;
    z-index: 2;
    font-size: 16px;
    font-weight: 300;
    color: $primary;
    @include mq(lg) {
      font-size: 22px;
    }
  }
  &::before {
    background: linear-gradient(
      92deg,
      rgba(49, 150, 147, 1) 31.45%,
      rgba(62, 189, 122, 1) 96.68%
    );
    position: absolute;
    content: '';
    inset: 0;
    z-index: 1;
    opacity: 0;
    transition: opacity linear 0.3s;
    border: 1px solid transparent;
    border-radius: 50px;
  }
  &:hover {
    border: 1px solid transparent;
    span {
      color: $white;
    }
    &::before {
      opacity: 1;
    }
  }
  @include mq(lg) {
    padding: 15px 25px;
  }

  .card & {
    @include mq(lg) {
      padding: 10px 20px;
      span {
        font-size: 16px;
      }
    }
  }
}
.button-item-container-secondary {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 20px;
  border-radius: 50px;
  border: 1px solid transparent;
  background: linear-gradient(
    92deg,
    rgba(49, 150, 147, 1) 31.45%,
    rgba(62, 189, 122, 1) 96.68%
  );
  cursor: pointer;
  position: relative;
  span {
    position: relative;
    z-index: 2;
    font-size: 16px;
    color: $white;
    font-weight: 300;
    @include mq(lg) {
      font-size: 22px;
    }
  }
  &::before {
    background: $white;
    position: absolute;
    content: '';
    inset: 0;
    z-index: 1;
    opacity: 0;
    transition: opacity linear 0.3s;
    border-radius: 50px;
    border: 1px solid transparent;
  }
  &:hover {
    border: 1px solid $primary;
    span {
      color: $primary;
    }
    &::before {
      opacity: 1;
    }
  }
  @include mq(lg) {
    padding: 15px 25px;
  }
}
.button-item-container-select {
  width: 100%;
  background-color: $primary;
  padding: 15px 20px;
  border: 1px solid transparent;
  border-radius: 5px;
  cursor: pointer;
  span {
    font-weight: 300;
    color: white;
    font-size: 16px;
  }
}
</style>
