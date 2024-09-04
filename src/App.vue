<template>
  <div id="app" class="container">
    <h1 class="text-center my-4">To-Do Listesi</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
  components: {
    TodoList
  }
};
</script>

<style scoped>
</style>
