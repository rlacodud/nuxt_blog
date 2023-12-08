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
import {ref} from "vue";
import Tag from "@/components/common/Tag.vue";

const tagList = ref(null)
const error = ref(null)

fetch('https://api.realworld.io/api/tags')
    .then((res) => res.json())
    .then((json) => (tagList.value = json.tags))
    .catch((err) => (error.value = err))

</script>

<style scoped>

</style>