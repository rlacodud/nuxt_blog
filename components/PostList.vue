<template>
  <div class="post_list_container">
    <template v-if="postList">
      <ul>
        <li v-for="(post, index) in postList" :key="index">
          <Post :post="post"/>
        </li>
      </ul>
    </template>
    <template v-else>
      loading...
    </template>
  </div>
</template>

<script setup>
import {ref} from "vue";
import Post from "@/components/common/Post.vue";

const postList = ref(null)
const error = ref(null)

fetch('https://api.realworld.io/api/articles')
    .then((res) => res.json())
    .then((json) => (postList.value = json.articles))
    .catch((err) => (error.value = err))
</script>

<style scoped>

</style>