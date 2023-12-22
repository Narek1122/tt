<template>
    <ul>
      <li v-for="comment in comments" :key="comment.id">
        {{ comment.text }}
        <CommentForm :parentId="comment.id" @submit-comment="submitNestedComment" />
        <ul v-if="comment.children.length > 0">
          <CommentList :comments="comment.children" @submit-nested-comment="submitNestedComment" />
        </ul>
      </li>
    </ul>
  </template>
  
  <script>
  import CommentForm from '~/components/CommentForm.vue';
  
  export default {
    props: ['comments'],
    components: { CommentForm },
    methods: {
      submitNestedComment(text, parentId) {
        // Make API request to submit a nested comment for the specified parent comment
      }
    }
  };
  </script>
  