<template>
  <!--<Link href="/listing">Listings</Link>&nbsp;
      <Link href="/listing/create">New Listing</Link>
      -->
      <header class="border-b border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-900 w-full">
    <div class="container mx-auto">
      <nav class="p-4 flex items-center justify-between">
        <div class="text-lg font-medium">
          <Link :href="route('listing.index')">Listings</Link>
        </div>
        <div class="text-xl text-indigo-600 dark:text-indigo-300 font-bold text-center">
          <Link :href="route('listing.index')">LaraZillow</Link>
        </div>
        <div>
          <Link :href="route('listing.create')" class="btn-primary">+ New Listing</Link>
        </div>
      </nav>
    </div>
  </header>

  <main class="container mx-auto p-4">
    <div>The page with time {{timer}}</div>
    <div v-if="flashSuccess" class="mb-4 border rounded-md shadow-sm border-green-200 dark:border-green-800 bg-green-50 dark:bg-green-900 p-2">
      {{ flashSuccess }}
    </div>
    <slot>Default</slot>
    
  </main>

<!--    <div v-if="flashSuccess" class="success">
    {{ flashSuccess }}
  </div>
    <slot>Default</slot>-->
  </template>
  <script setup>
  //import { Link } from '@inertiajs/vue3'
  import { computed } from 'vue'
import { Link, usePage } from '@inertiajs/vue3'
const page = usePage()
const flashSuccess = computed(
() => page.props.flash.success,
)


  import { ref } from 'vue'
const timer = ref(0)
setInterval(() => timer.value++, 1000)
</script>
