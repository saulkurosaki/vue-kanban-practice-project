<script setup>
import { reactive } from "vue";
import InputNew from "./InputNew.vue";

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

function handleNewItem(text, board) {
  board.items.push({
    id: crypto.randomUUID(),
    title: text.value,
  });
}
</script>

<template>
  <nav>
    <ul>
      <li><a href="#">Create Board</a></li>
    </ul>
  </nav>

  <div class="boards-container">
    <div class="boards">
      <div class="board" v-for="board in boards" :key="board.id">
        <div>{{ board.name }}</div>
        <InputNew @on-new-item="(text) => handleNewItem(text, board)" />
        <div class="items">
          <div class="item" v-for="item in board.items" :key="item.id">
            {{ item.title }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
nav {
  display: flex;
  flex-direction: row;
  align-items: center;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 70px;
  background-color: indigo;
}

nav li {
  list-style-type: none;
}

nav a {
  color: rgb(2, 204, 2);
  font-size: x-large;
  font-weight: 500;
  text-decoration: none;
}

nav a:hover {
  color: rgb(1, 168, 1);
}

.boards {
  display: flex;
  gap: 10px;
  margin-top: 70px;
}

.board {
  background-color: #efefef;
  padding: 10px;
}

.items {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.item {
  background-color: white;
  padding: 10px;
  box-sizing: border-box;
}
</style>
