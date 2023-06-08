<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

await router.push({ query: { 'test': 'abc' } })

</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
