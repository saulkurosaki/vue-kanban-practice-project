<script setup>
import { ref } from "@vue/reactivity";

const text = ref();

function handleSubmit() {
  if (text !== "") {
    //mandar a llamar el emit
  }
}
</script>

<template>
  <form action="" @submit.prevent="handleSubmit">
    <input type="text" v-bind="text" />
  </form>
</template>

<style scoped></style>
