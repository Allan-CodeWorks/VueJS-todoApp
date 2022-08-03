<script >

import TodoList from './components/todoList.vue'
import Counter from './components/counter.vue';

export default {
  data() {
    return {
      itemsTodo:
      {
        list: [
          "Afficher Titre",
          "Écrire liste",
          "Ajouter coche",
          "Écrire composant item",
          "Ajouter bouton add",
          "Ajouter feature delete line"
        ],
      },
      itemText: ''
    };
  },
  components: { TodoList, Counter }
}


</script>
<template>
  <header>
    <h1>Todo App</h1>
  </header>

  <main>

    <Counter v-bind:items="itemsTodo.list"></Counter>
    <div class="main_list">
      <TodoList :itemList="itemsTodo" />

    </div>
    <button v-on:click="itemsTodo.list.push(itemText)">Add Item</button>
    <input v-model="itemText" placeholder="New Item">

  </main>
</template>

<style scoped>
header {
  position: relative;
  margin: auto;
  text-align: center;
}

.main_list {
  margin: auto;
}
</style>
