<template>
  <div class="app">
    <todo-form @create="createTodo"></todo-form>
    <todo-list :todos="todos" @remove="removeTodo"></todo-list>
  </div>
</template>

<script>
import TodoForm from "@/components/TodoForm";
import TodoList from "@/components/TodoList";
export default {
  components: {
    TodoForm,
    TodoList
  },
  data() {
    return{
      todos: [
          {
            id: 1,
            title: 'Выполнить задачу 1'
          },
          {
            id: 2,
            title: 'Выполнить задачу 2'
          },
      ],
    }
  },
  methods: {
    createTodo(todo) {
      this.todos.push(todo);
    },
    removeTodo(todo) {
      this.todos = this.todos.filter(t => t.id !== todo.id);
    }
  }
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}



form {
  display: flex;
  flex-direction: column;
}
.btn {
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: orange;
  border: 2px solid orange;
  align-self: flex-end;
}

.input {
  width: 100%;
  border: 2px solid orange;
  padding: 10px;
  margin-top: 15px;
}

</style>