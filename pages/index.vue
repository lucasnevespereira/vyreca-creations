<template>
  <div>
    <h1>{{ merchant[0].name }}</h1>
    <h3>
      <n-link to="/categories">Categories</n-link>
    </h3>
    <CategoryList :categories="categories" />
    <h3>
      <n-link to="/products">Products</n-link>
    </h3>
    <ProductList :products="products" />
  </div>
</template>
<script>
export default {
  async asyncData({ $commerce }) {
    const { data: merchant } = await $commerce.merchants.about();
    const { data: categories } = await $commerce.categories.list();
    const { data: products } = await $commerce.products.list();
    return {
      merchant,
      categories,
      products,
    };
  },
};
</script>
