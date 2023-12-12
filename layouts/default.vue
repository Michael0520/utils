<script setup>
const router = useRouter();
const routes = router.getRoutes()
  .map(route => route.path)

</script>

<template>
  <div class="flex h-screen">
    <aside class="sidebar flex flex-col w-64 bg-slate-800 text-white shadow-lg">
      <div class="px-6 py-8">
        <h1 class="text-xl font-bold mb-8">Navigation</h1>
        <ul class="space-y-2">
          <li v-for="route in routes" :key="route" class="rounded-lg hover:bg-slate-700 bg-slate-600">
            <NuxtLink :to="route" class="block px-4 py-3 transition-colors duration-200 ease-in-out">
              {{ route.slice(1) }}
            </NuxtLink>
          </li>
        </ul>
      </div>
    </aside>
    <main class="flex flex-col w-full p-10 h-screen items-center justify-center text-center">
      <slot />
      <Footer />
      <div class="mx-auto mt-5 text-center text-sm opacity-50">
        [Custom Route Layout]
      </div>
    </main>
  </div>
</template>
