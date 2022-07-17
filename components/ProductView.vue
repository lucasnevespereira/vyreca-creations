<template>
  <div>
    <p>{{ product.name }}</p>
  </div>
</template>
<script>
export default {
  name: "ProductView",
  props: ["product"],
};
</script>
