<template>
  <div>
    <PostList :posts="posts" />
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get('YOUR_API_ENDPOINT/posts');
    return { posts };
  }
};
</script>
