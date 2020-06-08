<template>
  <div class="place">
    <img :src="location.img" width="235" height="300"/>
    <slot></slot>
    <p>{{ location.desc }}</p>
  </div>
</template>

<script>
  export default {
    name: 'Place',
    props: ['location']
  }
</script>

<style scoped>

</style>
