<script  setup>
const router = useRouter()
const routes = router.getRoutes()
  .map(route => route.path)
  .filter(path => path.includes('/navigation'))
</script>

<template>
  <aside class="sidebar">
    <ul>
      <li v-for="route in routes" :key="route">
        <NuxtLink :to="route">
          {{ route.slice(1) }}
        </NuxtLink>
      </li>
    </ul>
  </aside>
  <main class="px-10 py-20 text-center">
    <slot />
    <Footer />
    <div class="mx-auto mt-5 text-center text-sm opacity-25">
      [Custom Route Layout]
    </div>
  </main>
</template>
