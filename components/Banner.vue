<template>
  <div class="banner_container" :class="{banner_profile: isProfile}">
    <div class="container">
      <h1> conduit </h1>
      <p>A place to share your knowledge.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Banner",
  props: {
    isProfile: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>

</style>