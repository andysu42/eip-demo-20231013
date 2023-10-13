<script>
import { defineComponent } from 'vue'
import nested from '/@src/components/nested.vue'

export default defineComponent({
    components: {
      nestedDraggable: nested,
    },
    setup() {
      const enabled = ref(true)
      const list = ref([
      {
        "level": "a",
        "name": "技術處",
        "children": [
          {
            "level": "b",
            "name": "開發一部",
            "children": []
          },
          {
            "level": "b",
            "name": "開發二部",
            "children": []
          },
          {
            "level": "b",
            "name": "前端開發部",
            "children": []
          }
        ]
      },
      {
        "level": "a",
        "name": "營運處",
        "children": [
          {
            "level": "b",
            "name": "產品部",
            "children": [
              {
                "level": "c",
                "name": "視覺設計組",
                "children": []
              },
              {
                "level": "b",
                "name": "行銷部",
                "children": []
              },
            ]
          }
        ]
      },
      {
        "level": "a",
        "name": "財務處",
        "children": [
          {
            "level": "b",
            "name": "財務組",
            "children": []
          },
          {
            "level": "b",
            "name": "帳務組",
            "children": []
          },
        ]
      }
    ])

    const dragging = ref(false)

    const log = (event) => {
      console.log(event)
    }

    const options = ref(['All Flights', 'All Options'])

    const centeredActionsOpen = ref(false)

    const option4 = ref(true)

    const openUnitModal = (el) => {
      console.log(el, 'openUnitModal');
      centeredActionsOpen.value = true
    }

    return {
      enabled,
      list,
      dragging,
      log,
      options,
      centeredActionsOpen,
      option4,
      openUnitModal
    }
  },
})
</script>

<template>
  <div class="business-dashboard flights-dashboard">
    <div class="columns">
      <div class="column is-12">
        <!-- <div class="booking-bar-wrapper">
          <img
            class="travel-illustration light-image"
            src="/@src/assets/illustrations/dashboards/flights/travel.svg"
            alt=""
          >
          <img
            class="travel-illustration dark-image"
            src="/@src/assets/illustrations/dashboards/flights/travel-dark.svg"
            alt=""
          >
          <div class="booking-bar-info">
            <i
              aria-hidden="true"
              class="lnil lnil-plane-alt"
            />
            <div class="inner">
              <h2 class="booking-bar-heading">
                Paris <small>[PAR]</small> - New York
                <small>[NY]</small>
              </h2>
              <p class="booking-bar-sub-heading">
                1 adult - Business
              </p>
            </div>
          </div>
          <div class="booking-bar">
            <ClientOnly>
              <VDatePicker
                v-model="date"
                is-range
                color="green"
                trim-weeks
              >
                <template #default="{ inputValue, inputEvents }">
                  <div class="booking-bar-inputs">
                    <VControl icon="feather:calendar">
                      <input
                        type="text"
                        class="input flight-datepicker"
                        placeholder="Departure"
                        :value="inputValue.start"
                        v-on="inputEvents.start"
                      >
                    </VControl>
                    <VControl icon="feather:calendar">
                      <input
                        type="text"
                        class="input flight-datepicker"
                        placeholder="Return"
                        :value="inputValue.end"
                        v-on="inputEvents.end"
                      >
                    </VControl>
                  </div>
                </template>
              </VDatePicker>
            </ClientOnly>
          </div>
        </div> -->

        <!-- <div class="flights-toolbar">
          <h3 class="dark-inverted">
            74 results
          </h3>
          <FlightResultsDropdown />
        </div> -->

        <div class="flights-summary-wrapper">
          <div class="column">
            <div class="">
              <VButton
                bold
                @click="centeredActionsOpen = true"
              >
                ＋ 新增單位
              </VButton>
            </div>
          </div>
        </div>
        <!-- modal -->
        <VModal
          :open="centeredActionsOpen"
          actions="right"
          :noscroll="true"
          size="small"
          title="編輯單位"
          cancel-label="取消"
          @close="centeredActionsOpen = false"
        >
          <template #content>
            <div class="modal-form">
              <div class="field">
                <label>單位名稱 *</label>
                <div class="columns">
                  <div class="column">
                    <input
                      type="text"
                      class="input"
                      placeholder="輸入單位名稱"
                    >
                  </div>
                  <div class="column" />
                </div>
              </div>
              <div class="field">
                <label>單位職稱 *</label>
                <div class="columns">
                  <div class="column">
                    <input
                      type="text"
                      class="input"
                      placeholder="輸入單位職稱"
                    >
                  </div>
                  <div class="column">
                    <VButton
                      bold
                      rounded
                    >
                      新增
                    </VButton>
                  </div>
                </div>
              </div>
              <div class="field" />

              <VField
                grouped
                multiline
              >
                <VControl>
                  <VTags addons>
                    <VTag
                      label="Java工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                  <VTags addons>
                    <VTag
                      label="網路工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                  <VTags addons>
                    <VTag
                      label="網路工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                </VControl>
                <VControl>
                  <VTags addons>
                    <VTag
                      label="Java工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                  <VTags addons>
                    <VTag
                      label="網路工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                  <VTags addons>
                    <VTag
                      label="網路工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                </VControl>
                <VControl>
                  <VTags addons>
                    <VTag
                      label="Java工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                  <VTags addons>
                    <VTag
                      label="網路工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                  <VTags addons>
                    <VTag
                      label="網路工程師"
                      color="primary"
                    />
                    <VTag remove />
                  </VTags>
                </VControl>
              </VField>
            </div>
          </template>
          <template #action>
            <VButton
              color="primary"
              raised
            >
              儲存
            </VButton>
            <!-- <VButton color="danger">
              刪除
            </VButton> -->
          </template>
        </VModal>
        <!-- nestedDraggable -->
        <nestedDraggable
          :children="list"
          class="flights-summary-wrapper"
          @open-unit-modal="openUnitModal"
        />

        <!-- <div
          class="flights-summary-wrapper"
          style="margin-top: 100px;"
        >
          <div class="columns is-flex-tablet-p">
            <div class="column is-4">
              <a class="flight-summary">
                <div class="flight-price">312</div>
                <div class="meta">
                  <span>Cheapest</span>
                  <span>7h32min</span>
                </div>
              </a>
            </div>
            <div class="column is-4">
              <a class="flight-summary is-featured">
                <div class="flight-price">428</div>
                <div class="meta">
                  <span>Best</span>
                  <span>7h16min</span>
                </div>
              </a>
            </div>
            <div class="column is-4">
              <a class="flight-summary">
                <div class="flight-price">549</div>
                <div class="meta">
                  <span>Fastest</span>
                  <span>5h36min</span>
                </div>
              </a>
            </div>
          </div>
        </div> -->

        <!-- <div class="flights">
          <a class="flight-card">
            <img
              src="/@src/assets/illustrations/dashboards/flights/company1.svg"
              alt=""
            >
            <div class="start">
              <span>11:30 am</span>
              <span>Paris ORLY</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="route">
              <div class="departure" />
              <div
                class="line"
                data-content="1 stop"
              />
              <div class="arrival">
                <i
                  aria-hidden="true"
                  class="lnil lnil-plane-alt"
                />
              </div>
            </div>
            <div class="end">
              <span>06:59 pm</span>
              <span>New York JFK</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="flight-price">374</div>
          </a>

          <a class="flight-card">
            <img
              src="/@src/assets/illustrations/dashboards/flights/company2.svg"
              alt=""
            >
            <div class="start">
              <span>09:30 am</span>
              <span>Paris ORLY</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="route">
              <div class="departure" />
              <div
                class="line"
                data-content="1 stop"
              />
              <div class="arrival">
                <i
                  aria-hidden="true"
                  class="lnil lnil-plane-alt"
                />
              </div>
            </div>
            <div class="end">
              <span>04:18 pm</span>
              <span>New York JFK</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="flight-price">392</div>
          </a>

          <a class="flight-card">
            <img
              src="/@src/assets/illustrations/dashboards/flights/company1.svg"
              alt=""
            >
            <div class="start">
              <span>06:42 am</span>
              <span>Paris ORLY</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="route">
              <div class="departure" />
              <div
                class="line"
                data-content="direct"
              />
              <div class="arrival">
                <i
                  aria-hidden="true"
                  class="lnil lnil-plane-alt"
                />
              </div>
            </div>
            <div class="end">
              <span>02:11 pm</span>
              <span>New York JFK</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="flight-price">398</div>
          </a>

          <a class="flight-card">
            <img
              src="/@src/assets/illustrations/dashboards/flights/company3.svg"
              alt=""
            >
            <div class="start">
              <span>07:23 am</span>
              <span>Paris ORLY</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="route">
              <div class="departure" />
              <div
                class="line"
                data-content="direct"
              />
              <div class="arrival">
                <i
                  aria-hidden="true"
                  class="lnil lnil-plane-alt"
                />
              </div>
            </div>
            <div class="end">
              <span>01:46 pm</span>
              <span>New York JFK</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="flight-price">407</div>
          </a>

          <a class="flight-card">
            <img
              src="/@src/assets/illustrations/dashboards/flights/company1.svg"
              alt=""
            >
            <div class="start">
              <span>10:12 am</span>
              <span>Paris ORLY</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="route">
              <div class="departure" />
              <div
                class="line"
                data-content="1 stop"
              />
              <div class="arrival">
                <i
                  aria-hidden="true"
                  class="lnil lnil-plane-alt"
                />
              </div>
            </div>
            <div class="end">
              <span>03:39 pm</span>
              <span>New York JFK</span>
              <span>Monday, Jul 7th</span>
            </div>
            <div class="flight-price">431</div>
          </a>
        </div> -->
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import '/@src/scss/abstracts/all';

.flights-dashboard {
  .booking-bar-wrapper {
    @include vuero-s-card;

    position: relative;
    background: var(--primary);
    border-color: var(--primary);
    padding: 30px;
    color: var(--white);
    font-family: var(--font);
    box-shadow: var(--primary-box-shadow);

    .travel-illustration {
      position: absolute;
      bottom: 30px;
      inset-inline-end: 30px;
      max-width: 260px;
    }

    .booking-bar-info {
      display: flex;
      align-items: center;
      margin-bottom: 12px;

      .lnil {
        font-size: 2.2rem;
        color: var(--white);
      }

      .inner {
        margin-inline-start: 16px;

        .booking-bar-heading {
          font-family: var(--font-alt);
          font-size: 1.4rem;
          font-weight: 600;
          line-height: 1.2;
          color: var(--white);
        }

        .booking-bar-sub-heading {
          font-family: var(--font);
          font-weight: 500;
          font-size: 1.1rem;
          color: var(--white);
        }
      }
    }

    .booking-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;

      .booking-bar-inputs {
        display: flex;
        align-items: center;

        .control:not(:last-of-type) {
          margin-inline-end: 2rem;
        }

        .input {
          font-family: var(--font);
          color: var(--light-text);
        }
      }
    }
  }

  .flights-toolbar {
    padding: 16px 0;
    display: flex;
    align-items: center;
    justify-content: space-between;

    h3 {
      font-family: var(--font);
      font-weight: 600;
      color: var(--dark-text);
    }
  }

  .flights-summary-wrapper {
    .flight-summary {
      @include vuero-s-card;

      display: flex;
      align-items: center;
      border: 1px solid var(--fade-grey);
      transition: all 0.3s; // transition-all test

      &:hover {
        border-color: var(--primary);
      }

      &.is-featured {
        background: var(--primary);
        border-color: var(--primary);
        box-shadow: var(--primary-box-shadow);

        .flight-price {
          color: var(--white);
        }

        .meta {
          span {
            color: var(--white) !important;
          }
        }
      }

      .flight-price {
        font-family: var(--font);
        font-size: 2rem;
        font-weight: 700;
        color: var(--primary);

        &::before {
          content: '$';
          position: relative;
          inset-inline-end: 0;
          font-size: 1.2rem;
          font-weight: 700;
        }
      }

      .meta {
        margin-inline-start: 16px;
        line-height: 1.3;

        span {
          display: block;

          &:first-child {
            font-family: var(--font-alt);
            color: var(--dark-text);
            font-size: 0.8rem;
            font-weight: 700;
            text-transform: uppercase;
          }

          &:nth-child(2) {
            font-family: var(--font);
            color: var(--light-text);
            font-size: 0.9rem;
          }
        }
      }
    }
  }

  .flights {
    padding: 1.5rem 0;

    .flight-card {
      @include vuero-s-card;

      display: flex;
      align-items: center;
      margin-bottom: 1.5rem;
      box-shadow: none;

      &:hover,
      &:focus {
        box-shadow: var(--light-box-shadow);

        .route {
          .line {
            &::before,
            &::after {
              opacity: 1;
            }
          }
        }
      }

      > img {
        display: block;
        border-radius: var(--radius-rounded);
        max-width: 32px;
      }

      .start,
      .end {
        span {
          display: block;
          color: var(--dark-text);
          font-family: var(--font);

          &:first-child {
            font-family: var(--font-alt);
            font-weight: 600;
            color: var(--dark-text);
          }

          &:nth-child(2),
          &:nth-child(3) {
            font-family: var(--font);
            font-size: 0.9rem;
            color: var(--light-text);
          }
        }
      }

      .start {
        margin-inline-start: 1rem;
      }

      .end {
        margin-inline-start: auto;
        margin-inline-end: 1.5rem;
      }

      .route {
        flex-grow: 2;
        display: flex;
        align-items: center;
        max-width: 320px;
        margin: 0 auto;
        padding: 0 1rem;

        .departure {
          height: 16px;
          width: 16px;
          border-radius: var(--radius-rounded);
          border: 1px solid var(--light-text);
        }

        .line {
          position: relative;
          flex-grow: 2;
          height: 1px;
          border-bottom: 1.6px dashed var(--light-text);

          &::before,
          &::after {
            opacity: 0;
            pointer-events: none;
            transition: all 0.3s; // transition-all test
          }

          &::before {
            content: '';
            position: absolute;
            top: -14px;
            inset-inline-start: 50%;
            inset-inline-end: 50%;
            height: 10px;
            width: 1px;
            border-inline-end: 1px solid var(--light-text);
          }

          &::after {
            content: attr(data-content);
            position: absolute;
            top: -32px;
            inset-inline-start: 23%;
            width: 130px;
            font-size: 0.8rem;
            text-align: center;
            color: var(--light-text);
          }
        }

        .arrival {
          font-size: 1.8rem;
          transform: rotate(calc(var(--transform-direction) * 90deg));
          height: 26px;
          width: 26px;
          display: flex;
          justify-content: center;
          align-items: center;

          .lnil {
            position: relative;
            top: -4px;
            inset-inline-end: 5px;
            color: var(--light-text);
            margin-inline-start: 0.75rem;
          }
        }
      }

      .flight-price {
        font-family: var(--font);
        font-size: 1.8rem;
        font-weight: 600;
        color: var(--light-text);

        &::before {
          content: '$';
          position: relative;
          top: -8px;
          inset-inline-end: 0;
          font-size: 1.1rem;
          font-weight: 700;
        }
      }
    }
  }

  .company-card {
    @include vuero-s-card;

    padding: 30px;
    margin-bottom: 1.5rem;

    .v-avatar {
      display: block;
      margin: 0 auto;
    }
  }

  .filters-card {
    @include vuero-s-card;

    padding: 30px;
    margin-bottom: 1.5rem;

    .checkboxes-list {
      margin: 0;
      padding: 20px 0 0;

      .field {
        > h5 {
          font-family: var(--font-alt);
          font-weight: 600;
          font-size: 0.8rem;
          text-transform: uppercase;
          color: var(--dark-text);
          padding-bottom: 6px;
        }
      }

      .checkbox {
        padding: 8px 0;
      }
    }
  }
}

.is-dark {
  .flights-dashboard {
    .booking-bar-wrapper {
      @include vuero-card--dark;

      background: var(--dark-sidebar-light-4);
      border-color: var(--dark-sidebar-light-12);
      box-shadow: var(--light-box-shadow);
    }

    .flights-summary-wrapper {
      .flight-summary {
        @include vuero-card--dark;

        &:hover,
        &:focus {
          border-color: var(--primary) !important;
        }

        &.is-featured {
          background: var(--primary) !important;
          border-color: var(--primary) !important;
          box-shadow: var(--primary-box-shadow) !important;

          .flight-price {
            color: var(--white);
          }
        }

        .flight-price {
          color: var(--primary);
        }

        .meta {
          span {
            &:first-child {
              color: var(--dark-dark-text);
            }
          }
        }
      }
    }

    .flights {
      .flight-card {
        @include vuero-card--dark;

        .start,
        .end {
          span {
            &:first-child {
              color: var(--dark-dark-text);
            }
          }
        }
      }
    }

    .company-card,
    .filters-card {
      @include vuero-card--dark;
    }
  }
}

@media only screen and (width <= 767px) {
  .flights-dashboard {
    .booking-bar-wrapper {
      .travel-illustration {
        position: static;
        margin-bottom: 20px;
      }

      .booking-bar {
        > div {
          width: 100%;
        }

        .booking-bar-inputs {
          flex-direction: column;
          width: 100%;

          .control {
            margin: 0 !important;
            width: 100% !important;

            &:first-child {
              margin-bottom: 1rem !important;
            }
          }
        }
      }
    }

    .flights {
      padding-bottom: 0;

      .flight-card {
        flex-direction: column;

        &:last-child {
          margin-bottom: 0;
        }

        > img {
          max-width: 48px;
          margin-bottom: 12px;
        }

        .start,
        .end {
          text-align: center;
          margin: 10px auto;

          span {
            font-size: 1rem !important;
          }
        }

        .route {
          width: 100%;
          max-width: 100%;

          .line {
            &::before,
            &::after {
              display: none !important;
            }
          }
        }
      }
    }
  }
}

@media only screen and (width >= 768px) and (width <= 1024px) and (orientation: portrait) {
  .flights-dashboard {
    .booking-bar-wrapper {
      .travel-illustration {
        bottom: 30px;
        inset-inline-end: -25px;
        max-width: 215px;
      }
    }

    .flights {
      padding-bottom: 0;

      .flight-card {
        &:last-child {
          margin-bottom: 0;
        }
      }
    }
  }
}

@media only screen and (width >= 768px) and (width <= 1024px) and (orientation: landscape) {
  .flights-dashboard {
    .booking-bar-wrapper {
      .travel-illustration {
        bottom: 30px;
        inset-inline-end: -12px;
        max-width: 200px;
      }
    }

    .flights-summary-wrapper {
      .flight-summary {
        .flight-price {
          font-size: 2.2rem;
        }
      }
    }
  }
}

@media only screen and (width <= 1300px) and (orientation: landscape) {
  .flights-dashboard {
    .flights-summary-wrapper {
      .flight-summary {
        .flight-price {
          font-size: 2.2rem;
        }
      }
    }
  }
}

.dragArea {
  min-height: 60px;
  // outline: 1px dotted var(--primary);
  display: flex;
  flex-wrap: wrap;
  border-radius: 8px;
}
</style>
