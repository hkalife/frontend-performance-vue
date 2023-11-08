<script setup lang="ts">
import { defineProps } from 'vue';
import { faker } from '@faker-js/faker';

const props = defineProps<{
  numberOfRowsToRender: number;
}>();

const mockProductData = (): {
  id: string
  productName: string
  isbn: string
  price: string
  department: string
  description: string
}[] => {
  const dataArray = []
  
  for (let i = 0; i < props.numberOfRowsToRender; i++) {
    dataArray.push({
      id: faker.database.mongodbObjectId(),
      productName: faker.commerce.product(),
      isbn: faker.commerce.isbn(),
      price: faker.commerce.price(),
      department: faker.commerce.department(),
      description: faker.commerce.productDescription()
    })
  }

  return dataArray
}
</script>

<template>
  <div>
    <h3>Products</h3>
    <table id="shared-table" align="center">
      <tr>
        <th>ID</th>
        <th>Product name</th>
        <th>ISBN</th>
        <th>Price</th>
        <th>Department</th>
        <th>Description</th>
      </tr>
      <tr v-for="product in mockProductData()" :key="product.id">
        <td>{{ product.id }}</td>
        <td>{{ product.productName }}</td>
        <td>{{ product.isbn }}</td>
        <td>{{ product.price }}</td>
        <td>{{ product.department }}</td>
        <td>{{ product.description }}</td>
      </tr>
    </table>
  </div>
</template>
