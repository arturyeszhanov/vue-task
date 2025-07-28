<script setup lang="js">
{/* 
    products list 
    Task 0: вывести список продуктов в виде ul>li(имя продукта, цена)
    Task 1: Add product добавить продукт в список
    Task 2: Delete product удалить продукт из списка
    Task 3: Sort products сортировать продукты по цене (js Array.sort) 
*/}

const products = [{ id: 1, name: "Product 1", price: 100 }];









</script>

<template>
  <div class="container">
    <h1 class="text-light bg-dark p-2">Products</h1>
    <h5>Sort by price: <button>Asc</button></h5>
    <div>
      <input type="text" />
      <button class="btn btn-primary">Add product</button>
    </div>
    <ul>
      <li>
        <span>Product 1</span>
        <span>100</span>
        <button>Delete</button>
      </li>
    </ul>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');
.container {
  font-family: Roboto, sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 800px;
  margin: 50px auto;
  padding: 20px;
  border-radius: 15px;
  background: #f6f6f6;
}
</style>
