<template>
  <div class="tag" :class="{has_bg : hasBg}">
    <nuxt-link :to="'/' + title">
      <span>{{title}}</span>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: "Tag",
  props: {
    title: {
      type: String,
      default: ''
    },
    hasBg: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>

</style>