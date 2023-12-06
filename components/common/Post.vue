<template>
  <article class="post_container">
    <div class="post_head">
      <div class="user_info">
        <nuxt-link :to="`article/${post.slug}`">
          <div class="user_img">
            <img :src="post.author.image" :alt="post.author.username"/>
          </div>
        </nuxt-link>
        <div class="user_text">
          <nuxt-link :to="`article/${post.slug}`">
            <h6 class="user_name">{{post.author.username}}</h6>
          </nuxt-link>
          <p class="user_date">{{post.createdAt}}</p>
        </div>
      </div>
      <div class="favorite_button">
        <button role="button">
          <span>{{post.favoritesCount}}</span>
        </button>
      </div>
    </div>
    <div class="post_body">
      <nuxt-link :to="`article/${post.slug}`">
        <h2 class="title">{{post.title}}</h2>
        <h3 class="contents">{{post.description}}</h3>
      </nuxt-link>
    </div>
    <div class="post_foot">
      <nuxt-link :to="`article/${post.slug}`" class="read_more_button">Read more ...</nuxt-link>
      <nuxt-link :to="`article/${post.slug}`">
        <ul class="post_tag_list">
          <li v-for="(tag, index) in post.tagList" :key="index">
            <Tag :title="tag"/>
          </li>
        </ul>
      </nuxt-link>
    </div>
  </article>
</template>

<script>
import Tag from "@/components/common/Tag.vue";

export default {
  name: "Post",
  components: {Tag},
  props: {
    post: {
      type: Object
    }
  }
}
</script>

<style scoped>

</style>