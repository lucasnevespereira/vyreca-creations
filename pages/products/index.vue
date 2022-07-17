<template>
  <div>
    <h1>Products</h1>
    <ProductList :products="products" />
  </div>
</template>
<script>
export default {
  async asyncData({ $commerce }) {
    const { data: products } = await $commerce.products.list();
    return {
      products,
    };
  },
};
</script>
