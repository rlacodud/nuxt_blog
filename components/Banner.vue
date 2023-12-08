<template>
  <div class="banner_container" :class="{banner_profile: isProfile}">
    <div class="container">
      <template v-if="isProfile">
        <h1>{{title}}</h1>
        <AuthorProfile
          :slug="slug"
          :image="image"
          :username="username"
          :created-at="createdAt"
        />
      </template>
      <template v-else>
        <h1> conduit </h1>
        <p>A place to share your knowledge.</p>
      </template>
    </div>
  </div>
</template>

<script setup>
import AuthorProfile from "@/components/common/AuthorProfile.vue";

defineProps({
  isProfile: {
    type: Boolean,
    default: false
  },
  title: String,
  slug: String,
  username: String,
  image: String,
  createdAt: String
})
</script>

<style scoped>

</style>