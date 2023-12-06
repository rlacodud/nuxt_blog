<template>
  <div class="post_list_container">
    <ul>
      <li v-for="(post, index) in postList" :key="index">
        <Post :post="post"/>
      </li>
    </ul>
  </div>
</template>

<script>
import Post from "@/components/common/Post.vue";
import Tag from "@/components/common/Tag.vue";

export default {
  name: "PostList",
  components: {Tag, Post},
  data() {
    return {
      postList: [],
    }
  },
  async asyncData({ $axios }){
    const { data } = await $axios.get('https://api.realworld.io/api/articles');
  },
  async fetch(){
    const { data } = await this.$axios.get('https://api.realworld.io/api/articles');
    this.postList = data.articles;
  },
}
</script>

<style scoped>

</style>