<template>
<div>
  <div class="ui fixed menu">
    <div class="header item">
      <img src="./assets/logo.png" alt="logo">
    </div>
  </div>
  <div class="ui container">
  <h1>My todoList</h1>
  <!-- todoList component -->
  <todo-list></todo-list>
  </div>
</div>
</template>

<script>

import todoList from './components/todoList'

export default {
  name: 'app',
  components: {
    todoList
  }
}
</script>

<style scoped>
  .ui.container {
    padding-top: 100px;
  }
</style>
