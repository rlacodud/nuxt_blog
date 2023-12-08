<template>
  <div class="button" :class="isClass ? isClass : ''">
    <button role="button">
      <span>{{title}}</span>
    </button>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  isClass: String
})
</script>

<style scoped>

</style>