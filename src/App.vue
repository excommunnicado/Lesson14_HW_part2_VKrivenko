<template>
  <div class="app">
    <h1>Список покупок</h1>
    <div v-if="items.length === 0">
      <p>Список пуст. Пожалуйста, добавьте товар</p>
      <p>Укажите название необходимого товара ниже</p>
    </div>
    <ProductList :items="items" @remove="removeItem"></ProductList>
    <add-item @add="addItem"></add-item>
  </div>
</template>

<script>
import ProductList from "./components/ProductList.vue";
import AddItem from "./components/AddItem.vue";

export default {
  name: "App",
  components: {
    ProductList,
    AddItem,
  },
  data() {
    return {
      items: ["Яблоки", "Молоко", "Хлеб"],
    };
  },
  methods: {
    removeItem(index) {
      this.items.splice(index, 1);
    },
    addItem(item) {
      this.items.push(item);
    },
  },
};
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin: 0 10px;
}

.app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
