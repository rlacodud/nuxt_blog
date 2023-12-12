<template>
  <div>
    <Banner/>
    <div class="flex container main_container">
      <PostList :postList="postList"/>
      <TagList :tagList="tagList"/>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue";

const error = ref(null)

const tagList = ref(null)
const postList = ref(null)

fetch('https://api.realworld.io/api/articles')
    .then((res) => res.json())
    .then((json) => (postList.value = json.articles))
    .catch((err) => (error.value = err))

fetch('https://api.realworld.io/api/tags')
    .then((res) => res.json())
    .then((json) => (tagList.value = json.tags))
    .catch((err) => (error.value = err))
</script>
