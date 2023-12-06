<template>
  <div class="post_contents_container">
    <template v-if="postData">
      <Banner
      :title="postData.title"
      :isProfile="true"
      :slug="postData.slug"
      :image="postData.author.image"
      :username="postData.author.username"
      :created-at="createdAt"
      />
      <div class="container">
        <div class="post_contents_body">
          <p>{{postData.body}}</p>
          <ul class="post_tag_list">
            <li v-for="(tag, index) in postData.tagList" :key="index">
              <Tag :title="tag"/>
            </li>
          </ul>
        </div>
        <div class="post_contents_foot">
          <AuthorProfile
            :slug="postData.slug"
            :image="postData.author.image"
            :username="postData.author.username"
            :created-at="createdAt"
          />
          <p>
            <nuxt-link to="sign-in">Sign in</nuxt-link>
            or
            <nuxt-link to="sign-up">Sign up</nuxt-link>
            to add comments on this article.
          </p>
        </div>
      </div>
    </template>
    <template v-else class="container">
      loading...
    </template>
  </div>
</template>

<script>
import Tag from "@/components/common/Tag.vue";
import AuthorProfile from "@/components/common/AuthorProfile.vue";
import dayjs from 'dayjs';

export default {
  components: {AuthorProfile, Tag},
  data() {
    return {
      postData: null,
      createdAt: '',
    }
  },
  computed: {
    id() {
      return this.$route.params.id
    }
  },
  async fetch(){
    const { data } = await this.$axios.get(`https://api.realworld.io/api/articles/${this.$route.params.id}`);
    this.postData = data.article
      this.createdAt = dayjs(this.postData.createdAt).format('MMMM DD, YYYY')
    console.log('data', this.postData);
  },
}
</script>

<style scoped>

</style>