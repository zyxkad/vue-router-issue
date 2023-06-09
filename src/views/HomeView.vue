<script setup>
import { ref } from 'vue'
import { onBeforeRouteUpdate } from 'vue-router'
import TheWelcome from '../components/TheWelcome.vue'

const props = defineProps({
  'pageid': String,
})

function fetchPageData(pid){
  return `This is data of page ${pid}`
}

var data = ref(fetchPageData(props.pageid))

onBeforeRouteUpdate((to, from, next) => {
  console.log('onBeforeRouteUpdate:', to, from)
  next((iv) => {
    console.log('next: props.pageid:', props.pageid)
  })
})

</script>

<template>
  <main>
    <h1>{{data}}</h1>
    <!-- <TheWelcome /> -->
  </main>
</template>
