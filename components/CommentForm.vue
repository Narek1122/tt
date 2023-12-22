<template>
    <div>
      <textarea v-model="commentText" rows="4" cols="50" placeholder="Enter your comment"></textarea>
      <button @click="submitComment">Submit Comment</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        commentText: ''
      };
    },
    methods: {
      submitComment() {
        this.$emit('submit-comment', this.commentText);
        this.commentText = ''; // Clear the input after submission
      }
    }
  };
  </script>
  