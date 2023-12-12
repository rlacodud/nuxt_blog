<template>
  <div class="input_box">
    <label :for="id" v-show="isLabel">{{label}}</label>
    <input class="input"
      :id="id"
      :placeholder="placeholder"
      :value="value"
      :readonly="readonly"
      :disabled="disabled"
    />
  </div>
</template>

<script setup>
defineProps({
  id: {
    type: String,
    required: true
  },
  isLabel: {
    type: Boolean,
    default: false
  },
  label: String,
  placeholder: String,
  value: String,
  readonly: Boolean,
  disabled: Boolean
})
</script>

<style scoped>

</style>