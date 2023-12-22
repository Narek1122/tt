<!-- components/Header.vue -->

<template>
  <header>
    <nav>

      <template v-for="post in posts" :key="post.id">
        <nuxt-link :to="`/posts/${post.id}`">{{ post.title }}</nuxt-link>
      </template>
      <!-- Add more navigation links as needed -->
    </nav>
  </header>
</template>

<script>
export default {
  props: ['posts'], // Assuming you pass the list of posts as a prop
};
</script>

<style>
/* Header styles go here */
</style>
