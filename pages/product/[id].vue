<template>
  <div class="text-4xl">
    <Title>{{ data.title }}</Title>
    <Meta name="description" :content="`My page's ${data.title} description`" />

    <h1>Product</h1>
    <h2>{{ $route.params.id }}</h2>
    <h3>{{ data.title }}</h3>
    <p>{{ data.description }}</p>
    <img :src="data.image" alt="" />
  </div>
</template>

<script>
import { useRoute } from "vue-router"
export default defineNuxtComponent({
  setup() {
    const route = useRoute()
    const { data } = asyncData("product", () => $fetch(`https://fakestoreapi.com/products/${route.params.id}`))

    return { data }
  },
})
</script>
