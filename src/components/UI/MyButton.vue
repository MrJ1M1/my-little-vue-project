<template>
    <button class="btn btn-success">{{text}}</button>
  </template>
  
  <script>
  export default {
    name: 'my-button',
    props: {
        text: String
    },
    
  }
  </script>
  
  <style scoped>
    
  </style>