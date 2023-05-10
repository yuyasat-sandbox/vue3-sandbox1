<script setup>
defineProps({
  todos: Array,
});
const emit = defineEmits(["removeTodo"]);
const clickRemove = (index) => emit("removeTodo", index);
</script>
<template>
  <ul v-if="todos.length > 0">
    <li v-for="(todo, i) in todos" :key="i">{{ todo }} <span @click="clickRemove(i)" style="cursor: pointer;">x</span></li>
  </ul>
  <p v-else>※ Todoを追加してください。</p>
</template>