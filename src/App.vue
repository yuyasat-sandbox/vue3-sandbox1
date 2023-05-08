<script setup>
import { ref, computed } from "vue";

const answer = computed(() => 1 + 1);
const message = "ようこそ！";
const message2 = computed(
  () => `ようこそ！<strong>${myName.value}さん</strong>！`
);
const welcomeColor = "red";
const myName = ref("");

const number = ref(0);
const add = () => number.value++;

const todos = ref([]);
const newTodo = ref("");
const addTodo = () => {
  todos.value.push(newTodo.value);
  newTodo.value = "";
};
</script>
<template>
  <h1>Vue 3</h1>
  <p>1 + 1 = {{ answer }}</p>
  <p>お名前は？：<input type="text" size="30" v-model="myName" /></p>
  <p v-text="message" v-bind:style="{ color: welcomeColor }"></p>
  <p
    v-html="message2"
    :style="{ 'background-color': 'blue', color: 'white' }"
  ></p>
  <p v-html="myName"></p>
  <div>
    <input type="text" size="30" v-model="number" />
    <button @click="add()">+1</button>
  </div>
  <div>
    <input type="text" size="30" v-model="newTodo" />
    <button @click="addTodo()">追加</button>
  </div>
  <ul>
    <li v-for="(todo, i) in todos" :key="i">{{ todo }}</li>
  </ul>
</template>
