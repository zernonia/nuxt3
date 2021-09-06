<template>
  <div class="text-4xl">
    <h1>Product list</h1>
    <ul>
      <li v-for="product in data">
        <NuxtLink :to="`/product/${product.id}`">
          {{ product.title }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
export default defineNuxtComponent({
  setup() {
    const { data } = asyncData("product", () => $fetch("https://fakestoreapi.com/products/"))
    return { data }
  },
})
</script>
