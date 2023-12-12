<template>
  <div class="tag_container">
    <template v-if="tagList">
      <div class="tag_inner">
        <h6 class="title">Popular Tags</h6>
        <div class="tag_list_container">
          <ul>
            <li v-for="(tagItem, index) in tagList" :key="index">
              <Tag :title="tagItem" :has-bg="true"/>
            </li>
          </ul>
        </div>
      </div>
    </template>
    <template v-else>
      loading...
    </template>
  </div>
</template>

<script setup>
import Tag from "@/components/common/Tag.vue";

defineProps({
  tagList: Array
})
</script>

<style scoped>

</style>