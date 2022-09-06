<template>
  <div class="category-item-component">
    <p class="category-name" v-if="categoryData && categoryData.name">
      {{ categoryData.name }}
    </p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: ['categoryData'],
})
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.category-item-component {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 6px 16px;
  border: 1px solid $primary;
  background-color: $white;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color linear 0.3s;
  p {
    font-size: 16px;
  }
  &:hover {
    background-color: $green-100;
  }
}
</style>
