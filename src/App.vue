<template>
  <div class="app">
    <form @submit.prevent>
      <h1>Добавление товара</h1>
      <input
        v-bind:value="title"
        @input="title = $event.target.value"
        class="input"
        type="text"
        placeholder="Название"
      />
      <input
        v-bind:value="body"
        @input="body = $event.target.value"
        class="input"
        type="text"
        placeholder="Описание"
      />
      <button class="btn" @click="createProduct">Создание</button>
    </form>
    <div>
      <div class="product" v-for="product in products">
        <div><strong>Название: </strong>{{ product.title }}</div>
        <div><strong>Описание: </strong>{{ product.body }}</div>
      </div>
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
      title: "",
      body: "",
    };
  },
  methods: {
    createProduct() {
      const newProduct = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      };
      this.products.push(newProduct);
      this.title = "";
      this.body = "";
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
form {
  display: flex;
  flex-direction: column;
}
.product {
  padding: 15px;
  border: 2px solid mediumslateblue;
  margin-top: 15px;
}
.input {
  width: 100%;
  border: 1px solid mediumslateblue;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: mediumslateblue;
  border: 1px solid mediumslateblue;
}
</style>
