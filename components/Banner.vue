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

<script>
import AuthorProfile from "@/components/common/AuthorProfile.vue";
import UserProfile from "@/components/common/UserProfile.vue";

export default {
  name: "Banner",
  components: {UserProfile, AuthorProfile},
  props: {
    isProfile: {
      type: Boolean,
      default: false
    },
    title: {
      type: String
    },
    slug: {
      type: String
    },
    username: {
      type: String
    },
    image: {
      type: String
    },
    createdAt: {
      type: String
    }
  }
}
</script>

<style scoped>

</style>