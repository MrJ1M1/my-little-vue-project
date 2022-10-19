<template>
    <header>
      <h1>{{title}}</h1>
      <my-button @click="$emit('toggle-add-task')" :text="showVisible ? 'Close Task' : 'Add Task'"/>
    </header>
  </template>
  
  <script>
  export default {
    name: 'Header',
    props: {
        title: String,
        showVisible: Boolean
    },
    emits: ['toggle-add-task'],
  }
  </script>
  
  <style scoped>
    header{
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
  </style>