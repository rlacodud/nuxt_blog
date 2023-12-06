<template>
  <div class="button" :class="isClass ? isClass : ''">
    <button role="button">
      <span>{{title}}</span>
    </button>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    title: {
      type: String
    },
    isClass: {
      type: String
    }
  }
}
</script>

<style scoped>

</style>