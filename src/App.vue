<script setup lang="ts">
import PeopleList from './components/PeopleList.vue';
import ProductList from './components/ProductList.vue';

const numberOfRowsToRender = 5;
</script>

<template>
  <div>
    <h1>FRONTEND PERFORMANCE (VUE)</h1>

    <PeopleList :numberOfRowsToRender="numberOfRowsToRender" />
    <ProductList :numberOfRowsToRender="numberOfRowsToRender" />
  </div>
</template>

<style scoped>
h1 {
  text-align: center;
}
</style>
