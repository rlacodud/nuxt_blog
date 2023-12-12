<template>
  <ul class="flex tab_list">
    <li class="tab_item" v-for="(list, index) in tabList" :key="index" :class="{is_active : list.isActive, is_show : list.isShow}">
      <button>{{list.title}}</button>
    </li>
  </ul>
</template>

<script setup>
import {ref} from "vue";

const tabList = ref([
  {
    title: "Your Feed",
    isShow: false,
    isActive: false,
  },
  {
    title: "Global Feed",
    isShow: true,
    isActive: true,
  },
  {
    title: "",
    isShow: false,
    isActive: false,
  }
])
</script>

<style scoped>

</style>