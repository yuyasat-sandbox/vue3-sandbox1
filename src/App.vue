<script setup>
import { ref, computed } from 'vue';

const answer = computed(() => 1 + 1);
const message = 'ようこそ！';
const message2 = computed(() => `ようこそ！<strong>${myName.value}さん</strong>！`);
const welcomeColor = 'red';
const myName = ref('');

</script>
<template>
  <h1>Vue 3</h1>
  <p>1 + 1 = {{ answer }}</p>
  <p>お名前は？：<input type="text" size="30" v-model="myName"></p>
  <p v-text="message" v-bind:style="{ color: welcomeColor  }"></p>
  <p v-html="message2" :style="{ 'background-color': 'blue', color: 'white' }"></p>
  <p v-html="myName"></p>
</template>
