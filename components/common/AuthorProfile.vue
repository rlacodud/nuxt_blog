<template>
  <div class="flex author_profile">
    <UserProfile
        :slug="slug"
        :image="image"
        :username="username"
        :created-at="createdAt"
    />
    <div class="flex button_container">
      <Button is-class="follow_button" title="Follow Anah Benešová" />
      <Button is-class="favorite_button" title="Favorite Article " />
    </div>
  </div>
</template>

<script setup>
import UserProfile from "@/components/common/UserProfile.vue";
import Button from "@/components/common/Button.vue";

defineProps({
  slug: String,
  username: String,
  image: String,
  createdAt: String
})
</script>

<style scoped>

</style>