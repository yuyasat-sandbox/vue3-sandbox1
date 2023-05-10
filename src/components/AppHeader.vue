<script setup>
defineProps({
  color: String,
});
</script>

<template>
<header>
  <h1 :style="{ 'color': color }"><slot name="title">No Title</slot></h1>
</header>

</template>