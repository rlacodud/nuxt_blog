<template>
  <div class="post_list_container">
    <Tab/>
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
import Post from "@/components/common/Post.vue";
import Tab from "@/components/common/Tab.vue";

defineProps({
  postList: Array
})
</script>

<style scoped>

</style>