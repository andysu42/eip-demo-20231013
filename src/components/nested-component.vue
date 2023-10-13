<template>
  <div class="flex justify-center">
    <div class="w-4/12 mr-2">
      <nested-draggable :tasks="list" />
    </div>

    <rawDisplay
      class="w-64"
      :value="list"
    />
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import nestedDraggable from '/@src/components/nested.vue'
import rawDisplay from '/@src/components/rawDisplay.vue'
export default defineComponent({
  name: 'NestedExample',
  display: 'Nested',
  order: 15,
  components: {
    rawDisplay,
    nestedDraggable,
  },
  setup() {
    const list = ref([
      {
        name: 'task 1',
        tasks: [
          {
            name: 'task 2',
            tasks: [],
          },
        ],
      },
      {
        name: 'task 3',
        tasks: [
          {
            name: 'task 4',
            tasks: [],
          },
        ],
      },
      {
        name: 'task 5',
        tasks: [],
      },
    ])
    return { list }
  },
})
</script>
<style scoped></style>
