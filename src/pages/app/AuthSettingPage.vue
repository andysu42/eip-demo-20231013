<script setup lang="ts">
import { useViewWrapper } from '/@src/stores/viewWrapper'

const viewWrapper = useViewWrapper()
viewWrapper.setPageTitle('職稱權限設定')

useHead({
  title: 'Main Dashboard - My app',
})
</script>

<template>
  <div class="page-content-inner">
    <AuthSetting />
  </div>
</template>
