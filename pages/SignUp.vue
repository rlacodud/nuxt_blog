<template>
  <div class="container sign_container">
    <div class="title_container">
      <h1>Sign up</h1>
      <nuxt-link to="/signin">Have an account?</nuxt-link>
    </div>
    <div class="input_container">
      <form>
        <Input type="text" id="signUpUsername" placeholder="Username" :required="true"/>
        <Input type="email" id="signUpEmail" placeholder="Email" :required="true"/>
        <Input type="password" id="signUpPassword" placeholder="Password" :required="true"/>
        <Button class="flex" title="Sign up" is-class="btn-primary" size="btn-l"/>
      </form>
    </div>
  </div>
</template>

<script setup>
import Input from "@/components/common/Input.vue";
import Button from "@/components/common/Button.vue";
</script>

<style scoped>

</style>