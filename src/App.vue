<template>
  <div>
    <div class="product" v-for="product in products">
      <div><strong>Название: </strong>{{ product.title }}</div>
      <div><strong>Описание: </strong>{{ product.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        { id: 1, title: "DEMO1", body: "Черновое описание" },
        { id: 2, title: "DEMO2", body: "Черновое описание" },
        { id: 3, title: "DEMO3", body: "Черновое описание" },
      ],
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.product {
  padding: 15px;
  border: 2px solid mediumslateblue;
  margin-top: 15px;
}
</style>
