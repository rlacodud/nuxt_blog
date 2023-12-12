<template>
  <div class="nav_wrap">
    <div class="container">
      <header>
        <div class="nav_logo">
          <h1><nuxt-link to="/">conduit</nuxt-link></h1>
        </div>
        <div class="nav_list">
          <nav>
            <ul>
              <li v-for="(list, index) in navigationList" :key="index">
                <nuxt-link :to="list.path">{{list.name}}</nuxt-link>
              </li>
            </ul>
          </nav>
        </div>
      </header>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue";

const navigationList = ref([
  {
    path: "/",
    name: "Home",
  },
  {
    path: "/signin",
    name: "Sign in",
  },
  {
    path: "/signup",
    name: "Sign up",
  }
])
</script>

<style scoped>
</style>