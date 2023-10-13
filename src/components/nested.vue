<!-- eslint-disable vuejs-accessibility/no-static-element-interactions -->
<!-- eslint-disable vuejs-accessibility/click-events-have-key-events -->
<template>
  <div class="bg-white">
    <draggable
      class="dragArea is-flex"
      tag="ul"
      :list="children"
      :group="{ name: 'g1' }"
      @end="onEnd"
    >
      <li
        v-for="el in children"
        :key="el.name"
        class="kanban-column is-6"
        :class="{ 'm-2': el.level === 'a', 'kanban-card': el.level !== 'a' }"
      >
        <div class="column">
          <a
            class="flight-summary"
            style="width: 200px;"
          >
            <div class="content-wraper">
              <div class="content-title">{{ el.name }}</div>
              <div class="dropdown-wrapper">
                <VDropdown
                  icon="feather:more-vertical"
                  spaced
                  left
                >
                  <template #content>
                    <a
                      role="menuitem"
                      href="javascript:void(0)"
                      class="dropdown-item is-media"
                      @click="$emit('openUnitModal', el)"
                    >
                      <div class="icon">
                        <i
                          class="lnil lnil-pencil"
                          aria-hidden="true"
                        />
                      </div>
                      <div
                        class="meta"
                      >
                        <div>編輯單位</div>
                        <!-- <span>點擊以開啟編輯視窗</span> -->
                      </div>
                    </a>

                    <a
                      role="menuitem"
                      href="#"
                      class="dropdown-item is-media"
                    >
                      <div class="icon">
                        <i
                          class="lnil lnil-trash-can"
                          aria-hidden="true"
                        />
                      </div>
                      <div class="meta">
                        <span>
                          <div
                            @click="deleteUnit"
                          >刪除單位
                          </div>
                        </span>
                        <!-- <span>點擊以刪除單位</span> -->
                      </div>
                    </a>

                    <!-- <hr class="dropdown-divider"> -->

                    <!-- <a
                      role="menuitem"
                      href="#"
                      class="dropdown-item is-media"
                    >
                      <div class="icon">
                        <i
                          aria-hidden="true"
                          class="lnil lnil-cog"
                        />
                      </div>
                      <div class="meta">
                        <span>Settings</span>
                        <span>configuration options</span>
                      </div>
                    </a> -->
                  </template>
                </VDropdown>
              </div>
            </div>
          </a>
        </div>

        <nested-draggable
          :children="el.children"
          class="bg-gray-100"
          v-bind="$attrs"
        />
        <!-- @open-unit-modal="$emit('openUnitModal', el.children)" -->
      </li>
    </draggable>
  </div>
</template>
<script>
import { VueDraggableNext } from 'vue-draggable-next'
export default {
  name: 'NestedDraggable',
  components: {
    draggable: VueDraggableNext,
  },
  props: {
    children: {
      required: true,
      type: Array,
    }
  },
  // emits: ['openUnitModal'],
  setup() {
    const onEnd = (e) => {
      console.log(e, 'onEnd')
    }

    const deleteUnit = (e) => {
      console.log(e, 'delete')
    }

    return {
      onEnd,
      deleteUnit
    }
  }
}
</script>
<style lang="scss" scoped>
.is-dark .kanban-column {
  background: var(--dark-sidebar-light-15);
  border-color: var(--dark-sidebar-light-15);
}
.kanban-column {
  background: var(--white);
  border-radius: 8px;
  border: 1px solid var(--medium-grey);

  display: flex;
  flex-direction: column;
  align-self: start;
  margin: 0.5rem;
}
.content-wraper {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;

  .content-title {
  color: var(--primary);
}
}

.dropdown-wrapper {
  display: flex;
  justify-content: flex-end;
}

.kanban-card {
  background: #e3e4e5;
}

.is-dark .kanban-column .kanban-card, .is-dark .kanban-column .gu-transit {
  // background: var(--dark-sidebar-light-6);
  border-color: var(--dark-sidebar-light-6);
}

.dragArea {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  min-height: 100px;
  // border: 1px solid var(--medium-grey);
}
</style>
