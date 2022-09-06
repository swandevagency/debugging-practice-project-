<template>
  <div :class="['slides', wrapperClasses ? wrapperClasses: '']">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name:"CarouselSlide",
    props: {
      wrapperClasses: String
    }
  }
</script>

<style>

</style>