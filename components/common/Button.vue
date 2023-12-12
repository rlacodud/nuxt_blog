<template>
  <div class="button" :class="isClass ? isClass : ''">
    <button role="button" :class="size ? size : ''">
      <span>{{title}}</span>
    </button>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  isClass: String,
  size: String
})
</script>

<style scoped>

</style>