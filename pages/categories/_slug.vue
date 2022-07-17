<template>
  <div>
    <h1>{{ category.name }}</h1>
    <ProductList :products="products" />
  </div>
</template>
<script>
import commerce from "~/common/commerce.js";

export default {
  async asyncData({ params }) {
    const { slug } = params;
    const category = await commerce.categories.retrieve(slug, { type: "slug" });
    const { data: products } = await commerce.products.list({
      category_slug: slug,
    });
    return {
      category,
      products,
    };
  },
};
</script>
