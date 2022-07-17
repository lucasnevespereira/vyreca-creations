<template>
  <div>
    <h1>Products</h1>
    <ProductList :products="products" />
  </div>
</template>
<script>
import commerce from "~/common/commerce.js";

export default {
  async asyncData() {
    const { data: products } = await commerce.products.list();
    return {
      products,
    };
  },
};
</script>
