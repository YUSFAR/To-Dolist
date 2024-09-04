<template>
  <div class="todo-list">
    <form @submit.prevent="addTodo" class="input-group mb-3">
      <input v-model="newTodo" class="form-control" placeholder="Yeni yapılacak iş" />
      <button type="submit" class="btn btn-primary">Ekle</button>
    </form>
    <ul class="list-group">
      <TodoItem
        v-for="todo in filteredTodos"
        :key="todo.id"
        :todo="todo"
        @toggle="toggleTodo"
        @remove="removeTodo"
        class="list-group-item"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  name: 'TodoList',
  components: {
    TodoItem
  },
  data() {
    return {
      newTodo: '',
      todos: [
        { id: 1, text: 'Vue.js öğren', done: false },
        { id: 2, text: 'Projeyi tamamla', done: true }
      ],
      filter: 'all'
    };
  },
  computed: {
    filteredTodos() {
      if (this.filter === 'active') {
        return this.todos.filter(todo => !todo.done);
      } else if (this.filter === 'completed') {
        return this.todos.filter(todo => todo.done);
      }
      return this.todos;
    }
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim()) {
        this.todos.push({
          id: this.todos.length + 1,
          text: this.newTodo,
          done: false
        });
        this.newTodo = '';
        this.saveTodos();
      }
    },
    toggleTodo(todo) {
      todo.done = !todo.done;
      this.saveTodos();
    },
    removeTodo(todo) {
      this.todos = this.todos.filter(t => t.id !== todo.id);
      this.saveTodos();
    },
    saveTodos() {
      localStorage.setItem('todos', JSON.stringify(this.todos));
    }
  },
  mounted() {
    const savedTodos = localStorage.getItem('todos');
    if (savedTodos) {
      this.todos = JSON.parse(savedTodos);
    }
  }
};
</script>

<style scoped>
.todo-list {
  max-width: 500px;
  margin: 0 auto;
}
</style>
