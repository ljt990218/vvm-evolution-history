<script setup lang="ts">
defineOptions({
  name: 'Keepalive',
})

definePage({
  name: 'Keepalive',
  meta: {
    level: 2,
    title: '🧡 KeepAlive',
    i18n: 'home.keepAlive',
    keepAlive: true,
  },
})

const value = ref(10)
</script>

<template>
  <Container>
    <var-paper :elevation="2" class="mt-20 flex flex-col items-center p-10">
      <p class="text-center">
        {{ $t('keepAlive.label') }}
      </p>

      <var-counter v-model="value" />
    </var-paper>
  </Container>
</template>
