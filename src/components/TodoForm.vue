<template>
  <form @submit.prevent>
    <input v-model="todo.title" class="input" type="text" placeholder="Задача">
    <button class="btn" @click="createPost">Добавить</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      todo: {
        title: ''
      }
    }
  },
  methods: {
    createPost() {
      this.todo.id = Date.now();
      this.$emit('create', this.todo);
      this.todo = {
        title: ''
      };
    }
  }
}
</script>

<style scoped>

</style>