<script setup>
import { reactive } from "vue";

let boards = reactive([
  {
    id: crypto.randomUUID(),
    name: "Tablero 1",
    items: [
      {
        id: crypto.randomUUID(),
        title: "Feature de Archivos",
      },
      {
        id: crypto.randomUUID(),
        title: "Resolver Bug",
      },
    ],
  },
  {
    id: crypto.randomUUID(),
    name: "Tablero 2",
    items: [
      {
        id: crypto.randomUUID(),
        title: "Mandar Reporte",
      },
      {
        id: crypto.randomUUID(),
        title: "Code Review",
      },
    ],
  },
]);
</script>

<template></template>

<style scoped></style>
