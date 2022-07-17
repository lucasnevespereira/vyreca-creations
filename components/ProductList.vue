<template>
  <ul>
    <li v-for="product in products" :key="product.permalink">
      <n-link
        :to="{
          name: 'products-permalink',
          params: { permalink: product.permalink },
        }"
      >
        <ProductView :product="product" />
      </n-link>
    </li>
  </ul>
</template>
<script>
export default {
  name: "ProductList",
  props: ["products"],
};
</script>
