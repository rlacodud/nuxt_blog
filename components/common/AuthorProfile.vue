<template>
  <div class="author_profile">
    <UserProfile
        :slug="slug"
        :image="image"
        :username="username"
        :created-at="createdAt"
    />
    <div class="button_container">
      <Button is-class="follow_button" title="Follow Anah Benešová" />
      <Button is-class="favorite_button" title="Favorite Article " />
    </div>
  </div>
</template>

<script>
import UserProfile from "@/components/common/UserProfile.vue";
import Button from "@/components/common/Button.vue";

export default {
  name: "AuthorProfile",
  components: {Button, UserProfile},
  props: {
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