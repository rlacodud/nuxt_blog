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

<script>
export default {
  name: 'Header',
  data() {
    return {
      navigationList: [
        {
          path: "/",
          name: "Home",
        },
        {
          path: "/sign-in",
          name: "Sign in",
        },
        {
          path: "/sign-up",
          name: "Sign up",
        }
      ]
    }
  }
}
</script>

<style scoped>
</style>