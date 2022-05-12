<script>
import axios from "axios";

export default {
  data() {
    return {
      count: 1,
      products: [],
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      const result = await axios.get("http://dummyjson.com/products/");
      this.products = result.data.products;
      console.log(result.data.products);
    },
    increment() {
      this.count++;
    },
  },
};
</script>

<template>
  <div class="home px-6 py-4">
    <button
      @click="increment"
      class="bg-blue-500 hover:bg-blue-400 text-white font-bold py-2 px-4 border-b-4 border-blue-700 hover:border-blue-500 rounded"
    >
      Count+
    </button>
    <h3>Home</h3>
    <h3>{{ count }}</h3>
    <div v-for="product in products" :key="product.id">
      {{ product.title }}
    </div>
  </div>
</template>
