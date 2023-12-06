<template>
  <div>
    <Header/>
    <Banner/>
    <div class="container main_container">
      <PostList/>
      <TagList/>
    </div>
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import TagList from "~/components/TagList.vue";
import Banner from "~/components/Banner.vue";

export default {
  name: 'IndexPage',
  components: { Banner, Header,  TagList},
  data() {
    return {
    }
  },

}
</script>
