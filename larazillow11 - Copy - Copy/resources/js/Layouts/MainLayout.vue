<template>
      <Link href="/listing">Listings</Link>&nbsp;
      <Link href="/listing/create">New Listing</Link>

    <div v-if="flashSuccess" class="success">
    {{ flashSuccess }}
  </div>

    <div>The page with time {{timer}}</div>
    <slot>Default</slot>
  </template>
  <script setup>
  //import { Link } from '@inertiajs/vue3'
  import { computed } from 'vue'
import { Link, usePage } from '@inertiajs/vue3'
// const x = ref(0)
// const y = computed(() => x.value * 2)
const page = usePage()
const flashSuccess = computed(
() => page.props.flash.success,
)


  import { ref } from 'vue'
const timer = ref(0)
setInterval(() => timer.value++, 1000)
</script>
<style scoped>
  .success {
    background-color: green;
    color: white;
  }
</style>