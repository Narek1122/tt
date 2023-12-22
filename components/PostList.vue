<template>
  <div>
    <div v-for="post in posts" :key="post.id">
      <img :src="post.image" alt="Post Image" />
      <h2>{{ post.title }}</h2>
      <p>{{ post.miniDescription }}</p>
      <nuxt-link :to="`/posts/${post.id}`">View Details</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get('https://your-api-endpoint/posts');
    return { posts };
  },
};
</script>
