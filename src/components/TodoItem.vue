<template>
  <li :class="{ done: todo.done }" class="todo-item d-flex justify-content-between align-items-center">
    <div class="form-check">
      <input type="checkbox" v-model="todo.done" @change="$emit('toggle', todo)" class="form-check-input" />
      <label class="form-check-label">{{ todo.text }}</label>
    </div>
    <button @click="$emit('remove', todo)" class="btn btn-danger btn-sm">Sil</button>
  </li>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
.todo-item.done .form-check-label {
  text-decoration: line-through;
  color: #aaa;
}
</style>
