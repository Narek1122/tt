<template>
    <div>
      <img :src="post.image" alt="Post Image" />
      <h1>{{ post.title }}</h1>
      <p>{{ post.description }}</p>
      <p>{{ post.date }}</p>
      <CommentForm :postId="post.id" @submit-comment="submitComment" />
      <div v-if="post.comments.length > 0">
        <h2>Comments</h2>
        <CommentList :comments="post.comments" @submit-nested-comment="submitNestedComment" />
      </div>
    </div>
  </template>
  
  <script>
  import CommentForm from '~/components/CommentForm.vue';
  import CommentList from '~/components/CommentList.vue';
  
  export default {
    async asyncData({ $axios, params }) {
      const post = await $axios.$get(`https://your-api-endpoint/posts/${params.id}`);
      return { post };
    },
    components: { CommentForm, CommentList },
    methods: {
      submitComment(text) {
        // Make API request to submit a comment for the post
      },
      submitNestedComment(text, parentId) {
        // Make API request to submit a nested comment for the specified parent comment
      }
    }
  };
  </script>
  