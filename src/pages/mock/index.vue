<script setup lang="ts">
import { queryProse } from '@/api'

definePage({
  name: 'mock',
  meta: {
    level: 2,
    title: '💿 Mock 指南',
    i18n: 'home.mockGuide',
  },
})

const messages = ref<string>('')

function pull() {
  queryProse().then((res) => {
    messages.value = res.data.prose
  })
}

// reset data
const reset = () => messages.value = ''
</script>

<template>
  <Container>
    <div class="data-label">
      {{ $t('mock.fromAsyncData') }}
    </div>

    <div class="data-content bg-white dark:bg-[--van-background-2]">
      <div v-if="messages">
        {{ messages }}
      </div>
      <div v-else class="text-center color-#969799">
        {{ $t('mock.noData') }}
      </div>
    </div>

    <var-space class="m-10" direction="column">
      <var-button type="primary" block @click="pull">
        {{ $t('mock.pull') }}
      </var-button>
      <var-button type="default" block @click="reset">
        {{ $t('mock.reset') }}
      </var-button>
    </var-space>
  </Container>
</template>

<style lang="less" scoped>
.data-label {
  color: #969799;
  font-weight: 400;
  font-size: 14px;
  line-height: 16px;
  margin-top: 10px;
}

.data-content {
  height: 300px;
  padding: 20px;
  line-height: 30px;
  margin-top: 20px;
  font-size: 16px;
  border-radius: 15px;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
