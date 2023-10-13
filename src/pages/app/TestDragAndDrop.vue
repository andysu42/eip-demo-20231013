<script setup lang="ts">
import { useViewWrapper } from '/@src/stores/viewWrapper'

const viewWrapper = useViewWrapper()
viewWrapper.setPageTitle('組織架構設定')

useHead({
  title: 'Main Dashboard - My app',
})
</script>

<template>
  <div class="page-content-inner">
    <DragAndDrop2 />
  </div>
</template>
