<template>
  <div v-bind:style="{backgroundColor: activeColor}" class="todo">
    <div>
      <div><strong>Задача:</strong> {{ todo.title }}</div>
    </div>
    <div class="todo__btns">
      <button @click="applyTodo"><fa class="fa-2x" color="lightgreen" icon="check"/></button>
      <button @click="cancelTodo"><fa class="fa-2x" color="tomato" icon="x"/></button>
      <button @click="$emit('remove', todo)"><fa class="fa-2x" icon="trash-can"/></button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeColor: 'white',
    }
  },
  props: {
    todo: {
      type: Object,
      required: true,
    }
  },
  methods: {
    applyTodo() {
      this.activeColor = 'green'
    },
    cancelTodo() {
      this.activeColor = 'red'
    }
  }
}
</script>

<style scoped>

button {
  border: none;
  background: none;
  margin-left: 20px;
}

.todo{
  padding: 15px;
  border: 2px solid orange;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

</style>