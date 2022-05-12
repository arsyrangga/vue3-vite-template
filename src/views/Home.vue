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
    <!-- tombol untuk memanggil function increment -->
    <button
      @click="increment"
      class="bg-blue-500 hover:bg-blue-400 text-white font-bold py-2 px-4 border-b-4 border-blue-700 hover:border-blue-500 rounded"
    >
      Count+
    </button>
    <h3>Home</h3>

    <!-- Data count -->
    <h3>{{ count }}</h3>

    <!-- buat ternari operation render -->
    <div
      v-html="
        products.length > 0
          ? '<h3>Teks Ini Muncul setelah data muncul</h3>'
          : ''
      "
    ></div>

    <!-- buat Mapping Array -->
    <div v-for="product in products" :key="product.id">
      {{ product.title }}
    </div>
  </div>
</template>
