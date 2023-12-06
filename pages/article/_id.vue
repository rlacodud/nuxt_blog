<template>
  <p>
  </p>
</template>

<script>
export default {
  data() {
    return {
      targetPost: {},
    }
  },
  computed: {
    id() {
      return this.$route.params.id
    }
  },
  async fetch(){
    const { data } = await this.$axios.get('https://api.realworld.io/api/articles');
    this.targetPost = data.articles.filter(v => v.slug === this.$route.params.id)
    console.log(this.targetPost)
  },
}
</script>

<style scoped>

</style>