<template>
    <div id="app">
      <Form />
    </div>
  </template>
  
  <script>
  import { defineComponent } from 'vue'
  import Form from './components/Form.vue'
  
  export default defineComponent({
    name: 'App',
    components: {
      Form
    }
  })
  </script>
  
  <style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }
  </style>