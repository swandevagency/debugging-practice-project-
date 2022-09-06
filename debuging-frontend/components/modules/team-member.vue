<template>
  <div class="team-member-item-container">
    <img :src="pictureUrl" :alt="name" />
    <p>{{ name }}</p>
    <small>{{ role }}</small>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    name: {
      type: String,
      default: () => 'team member name',
    },
    role: {
      type: String,
      default: () => 'team member role',
    },
    pictureUrl: {
      type: String,
    },
  },
})
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.team-member-item-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  img {
    border-radius: 10px;
    width: 150px;
    height: 150px;
  }
  p {
    margin-top: 15px;
    margin-bottom: 10px;
  }
  small {
    font-size: 10px;
    color: #b1b1b1;
    font-weight: 400;
  }
}
@include mq(lg) {
  .team-member-item-container {
    img {
      width: 220px;
      height: 220px;
    }
    small {
      font-size: 12px;
    }
  }
}
</style>
