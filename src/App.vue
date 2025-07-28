<script setup lang="js">
{/* 
    products list 
    Task 0: вывести список продуктов в виде ul>li(имя продукта, цена)
    Task 1: Add product добавить продукт в список
    Task 2: Delete product удалить продукт из списка
    Task 3: Sort products сортировать продукты по цене (js Array.sort) 
*/}

import { ref } from 'vue';
const products = ref([
  {
    id: 1, 
    name: "Product 1", 
    price: 100
  }
  ]);

const productName = ref('')
const productPrice = ref('')

function addNewProduct() {
  products.value.push({id:Math.random(), name: productName.value, price: productPrice.value})
}

function deleteProduct(id) {
  products.value = products.value.filter(product => product.id !== id)
}

function sortAsc() {
  products.value.sort((a, b) => a.price - b.price);
}

function sortDesc() {
  products.value.sort((a, b) => b.price - a.price);
}
</script>

<template>
  <div class="container">
    <div class="w-50 d-flex flex-column flex-wrap align-items-start pe-5 border-end">
      <h1 class="text-white bg-dark mb-3 p-2 w-100">Products</h1>
      <ul>
        <li v-for="item in products" :key="item.id" >
          <span class="pe-2 text-break" > {{ item.name}} </span>
          <span class="text-decoration-underline"> {{ item.price}} </span>
          <button class="btn btn-sm btn-outline-danger m-2" @click="deleteProduct(item.id)" >Delete</button>
        </li>
      </ul>
    </div>
    <div class="w-50 d-flex flex-column align-items-start justify-content-start ps-4">
      <h5>Sort by price: 
        <button @click="sortAsc" class="ms-1 btn btn-outline-success">Asc</button>
        <button @click="sortDesc" class="ms-1 btn btn-outline-danger"> Desc</button>
      </h5>
      <hr />
      <h5>Add New Product</h5>
      <div class="d-flex align-items-center mt-2">
        <input type="text" class="form-control me-1" v-model="productName" />
        <input type="number" class="form-control" v-model="productPrice" />
        <button @click="addNewProduct" class="btn btn-primary ms-2 text-nowrap">Add</button>
      </div>
    </div>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

*,
*::before,
*::after {
  box-sizing: border-box;
}

.container {
  font-family: Roboto, sans-serif;
  display: flex;
  align-items: start;
  justify-content: space-between;
  gap: 20px;
  max-width: 800px;
  width: 100%;
  margin: 50px auto;
  padding: 40px;
  border-radius: 15px;
  background: #f6f6f6;
}
</style>
