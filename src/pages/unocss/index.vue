<script setup lang="ts">
definePage({
  name: 'unocss',
  meta: {
    level: 2,
    title: '🎨 Unocss 示例',
    i18n: 'home.unocssExample',
  },
})
</script>

<template>
  <Container>
    <var-paper :elevation="2" class="mt-20 flex flex-col items-center p-10">
      <h1 class="text-6xl color-pink font-semibold">
        Hello, Unocss!
      </h1>

      <p class="mt-4 text-gray-700 dark:text-white">
        This is a simple example of Unocss in action.
      </p>

      <button class="btn">
        Button
      </button>
    </var-paper>
  </Container>
</template>
