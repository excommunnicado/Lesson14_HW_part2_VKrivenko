<template>
  <ul class="product-list">
    <li v-for="(item, index) in items" :key="index" @click="removeItem(index)">
      {{ item }}
    </li>
  </ul>
</template>

<script>
export default {
  name: "ProductList",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  methods: {
    removeItem(index) {
      this.$emit("remove", index);
    },
  },
};
</script>

<style scoped lang="scss">
.product-list {
  list-style-type: none;
  padding: 0;
}
.product-list li {
  cursor: pointer;
}
</style>
