<template>Page visits: {{ data.count }}</template>

<script>
export default defineNuxtComponent({
  setup() {
    const { data } = asyncData("time", () => $fetch("/api/count"))
    return { data }
  },
})
</script>
