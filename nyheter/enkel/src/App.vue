<template>
  <main>
    <Suspense>
      <template #default>
        <News />
      </template>

      <template #fallback>
        <span>Laster inn nyhetene...</span>
      </template>
    </Suspense>
  </main>
</template>

<script setup>
import News from "./components/News.vue";
</script>
