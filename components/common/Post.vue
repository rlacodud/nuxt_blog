<template>
  <article class="post_container">
    <div class=" flex post_head">
      <UserProfile
          :slug="post.slug"
          :image="post.author.image"
          :username="post.author.username"
          :created-at="post.createdAt"
      />
      <Button is-class="favorite_button" :title="post.favoritesCount" />
    </div>
    <div class="post_body">
      <nuxt-link :to="`article/${post.slug}`">
        <h2 class="title">{{post.title}}</h2>
        <h3 class="contents">{{post.description}}</h3>
      </nuxt-link>
    </div>
    <div class="flex post_foot">
      <nuxt-link :to="`article/${post.slug}`" class="read_more_button">Read more ...</nuxt-link>
      <nuxt-link :to="`article/${post.slug}`">
        <ul class="flex post_tag_list">
          <li v-for="(tag, index) in post.tagList" :key="index">
            <Tag :title="tag"/>
          </li>
        </ul>
      </nuxt-link>
    </div>
  </article>
</template>

<script setup>
import UserProfile from "@/components/common/UserProfile.vue";
import Tag from "@/components/common/Tag.vue";
import Button from "@/components/common/Button.vue";

defineProps({
  post: Object
})
</script>

<style scoped>

</style>