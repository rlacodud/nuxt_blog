<template>
  <div class="user_info">
    <nuxt-link :to="`article/${slug}`">
      <div class="user_img">
        <img :src="image" :alt="username"/>
      </div>
    </nuxt-link>
    <div class="user_text">
      <nuxt-link :to="`article/${slug}`">
        <h6 class="user_name">{{username}}</h6>
      </nuxt-link>
      <p class="user_date">{{createdAt}}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  slug: String,
  username: String,
  image: String,
  createdAt: String
})
</script>

<style scoped>

</style>