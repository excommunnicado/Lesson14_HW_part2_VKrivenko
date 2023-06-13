<template>
  <div class="add-item">
    <input type="text" v-model="newItem" placeholder="Что покупаем?" />
    <button @click="addItem">Добавить</button>
  </div>
</template>

<script>
export default {
  name: "AddItem",
  data() {
    return {
      newItem: "",
    };
  },
  methods: {
    addItem() {
      if (this.newItem.trim() !== "") {
        this.$emit("add", this.newItem.trim());
        this.newItem = "";
      }
    },
  },
};
</script>

<style scoped lang="scss">
.add-item {
  margin-top: 20px;
}
.add-item input[type="text"] {
  width: 200px;
}
.add-item button {
  margin-left: 10px;
}
</style>
