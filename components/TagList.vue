<template>
  <div class="tag_container">
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
  </div>
</template>

<script>
import Tag from "~/components/common/Tag.vue";

export default {
  name: 'TagList',
  components: {Tag},
  data() {
    return {
      tagList: [],
    }
  },
  async asyncData({ $axios }){
    const { data } = await $axios.get('https://api.realworld.io/api/tags');
  },
  async fetch(){
    const { data } = await this.$axios.get('https://api.realworld.io/api/tags');
    this.tagList = data.tags
  },
}
</script>

<style scoped>

</style>