<template>
  <div>
    <ul>
      <TodoItem
        v-for="(todo, index) of todos"
        v-bind:index="index"
        v-bind:todo="todo"
        v-bind:key="todo.id"
        v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue';

export default {
  props: ['todos'],
  components: {
    TodoItem,
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id);
    },
  },
};
</script>

<style scoped>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
</style>
