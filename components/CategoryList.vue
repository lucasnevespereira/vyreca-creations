<template>
  <ul>
    <li v-for="category in categories" :key="category.slug">
      <n-link
        :to="{
          name: 'categories-slug',
          params: { slug: category.slug },
        }"
      >
        <CategoryView :category="category" />
      </n-link>
    </li>
  </ul>
</template>
<script>
export default {
  name: "CategoryList",
  props: ["categories"],
};
</script>
