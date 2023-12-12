<script setup lang="ts">
const { state, next, prev } = useCycleList([
  'Dog',
  'Cat',
  'Lizard',
  'Shark',
  'Whale',
  'Dolphin',
  'Octopus',
  'Seal',
])

</script>

<template>
  <div>
    <Logos mb-6 />
    <h1 class="text-primary text-unset text-4xl mb-6">vue/use : useCycleList</h1>
    <Suspense>
      <ClientOnly>
        <div>
          <div class="text-primary text-lg font-bold m-4">
            State : {{ state }}
          </div>
          <div class="flex items-center justify-center gap-4">
            <button class="btn" @click="prev()">
              Prev
            </button>
            <button class="btn" @click="next()">
              Next
            </button>

          </div>
        </div>
      </ClientOnly>
    </Suspense>

  </div>
</template>
