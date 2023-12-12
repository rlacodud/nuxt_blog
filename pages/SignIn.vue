<template>
  <div class="container sign-in_container">
    <div class="title_container">
      <h1>Sign in</h1>
      <nuxt-link to="/register">Need an account?</nuxt-link>
    </div>
    <div class="input_container">
      <form>
        <Input id="email" placeholder="Email" :required="true"/>
        <Input id="password" placeholder="Password" :required="true"/>
        <Button class="flex" title="Sign in" is-class="btn-primary" size="btn-l"/>
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