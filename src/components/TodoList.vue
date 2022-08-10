<template>
  <h3>Список задач</h3>
  <todo-item v-for="todo in todos" :todo="todo" :key="todo.id" @remove="$emit('remove', todo)"></todo-item>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
  components: {
    TodoItem
  },
  props: {
    todos: {
      type: Array,
      required: true,
    }
  }
}
</script>

<style scoped>



</style>