<!-- Please remove this file from your project -->
<template>
  <div>
    <!-- <h1>{{ post.title }}</h1> -->
    <h1>Hello</h1>
    <p>{{ post }}</p>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    let post = null
     post = await $axios.$get(`https://api.nuxtjs.dev/posts/1`)
    // eslint-disable-next-line no-console
    console.log("post", post);
    return { post }
  }
}
</script>