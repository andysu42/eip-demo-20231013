<script setup lang="ts">
const input = ref('')
const input2 = ref('')
const input3 = ref('')
const input4 = ref('')

const options = ref(false)

</script>

<template>
  <div class="business-dashboard flights-dashboard">
    <div class="columns">
      <div class="column is-10">
        <div class="flights-summary-wrapper">
          <div class="columns is-flex-tablet-p">
            <div class="column is-3">
              <!-- <a class="flight-summary">
                <div class="flight-price">312</div>
                <div class="meta">
                  <span>Cheapest</span>
                  <span>7h32min</span>
                </div>
              </a> -->
              <VField>
                <VLabel>處室</VLabel>
                <VControl>
                  <VSelect v-model="input">
                    <VOption value="">
                      選擇處室
                    </VOption>
                    <VOption value="Superman">
                      技術處
                    </VOption>
                    <VOption value="Batman">
                      營運處
                    </VOption>
                    <VOption value="Spiderman">
                      財務處
                    </VOption>
                  </VSelect>
                </VControl>
              </VField>
            </div>
            <div class="column is-3">
              <!-- <a class="flight-summary is-featured">
                <div class="flight-price">428</div>
                <div class="meta">
                  <span>Best</span>
                  <span>7h16min</span>
                </div>
              </a> -->
              <VField>
                <VLabel>部門</VLabel>
                <VControl>
                  <VSelect v-model="input2">
                    <VOption value="">
                      選擇部門
                    </VOption>
                    <VOption value="Superman">
                      開發一部
                    </VOption>
                    <VOption value="Batman">
                      開發二部
                    </VOption>
                    <VOption value="Spiderman">
                      前端開發部
                    </VOption>
                  </VSelect>
                </VControl>
              </VField>
            </div>
            <div class="column is-3">
              <!-- <a class="flight-summary">
                <div class="flight-price">549</div>
                <div class="meta">
                  <span>Fastest</span>
                  <span>5h36min</span>
                </div>
              </a> -->
              <VField>
                <VLabel>組別</VLabel>
                <VControl>
                  <VSelect v-model="input3">
                    <VOption value="">
                      選擇組別
                    </VOption>
                    <VOption value="Superman">
                      產品組
                    </VOption>
                    <VOption value="Batman">
                      專案組
                    </VOption>
                  </VSelect>
                </VControl>
              </VField>
            </div>
            <div class="column is-3">
              <!-- <a class="flight-summary">
                <div class="flight-price">549</div>
                <div class="meta">
                  <span>Fastest</span>
                  <span>5h36min</span>
                </div>
              </a> -->
              <VField>
                <VLabel>職稱</VLabel>
                <VControl>
                  <VSelect v-model="input4">
                    <VOption value="">
                      java工程師
                    </VOption>
                    <VOption value="Superman">
                      前端工程師
                    </VOption>
                    <VOption value="Batman">
                      網路工程師
                    </VOption>
                  </VSelect>
                </VControl>
              </VField>
            </div>
          </div>
        </div>
        <VField
          class="is-flex"
          style="margin-top: 60px;"
        >
          <VControl
            raw
            subcontrol
          >
            <VCheckbox
              v-model="options"
              :true-value="{ name: 'option2', label: 'Option 2' }"
              label="組織管理"
              color="primary"
              solid
            />
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="組織架構設定"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="職稱權限設定"
                color="primary"
                solid
              />
            </VControl>
          </VControl>
          <VControl
            raw
            subcontrol
          >
            <VCheckbox
              v-model="options"
              :true-value="{ name: 'option2', label: 'Option 2' }"
              label="員工資料管理"
              color="primary"
              solid
            />
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="人員建立"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="人員查詢"
                color="primary"
                solid
              />
            </VControl>
          </VControl>
          <VControl
            raw
            subcontrol
          >
            <VCheckbox
              v-model="options"
              :true-value="{ name: 'option2', label: 'Option 2' }"
              label="線上請假"
              color="primary"
              solid
            />
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="我的假單"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="申請假單"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="取消假單"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="申請銷假"
                color="primary"
                solid
              />
            </VControl>
          </VControl>
          <VControl
            raw
            subcontrol
          >
            <VCheckbox
              v-model="options"
              :true-value="{ name: 'option2', label: 'Option 2' }"
              label="考勤記錄查詢"
              color="primary"
              solid
            />
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="單位人員打卡記錄"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="單位人員請假記錄"
                color="primary"
                solid
              />
            </VControl>
          </VControl>
        </VField>
        <VField
          class="is-flex"
          style="margin-top: 60px;"
        >
          <VControl
            raw
            subcontrol
          >
            <VCheckbox
              v-model="options"
              :true-value="{ name: 'option2', label: 'Option 2' }"
              label="考勤記錄管理"
              color="primary"
              solid
            />
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="打卡記錄查詢"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="特休時數查詢"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="請假記錄查詢"
                color="primary"
                solid
              />
            </VControl>
          </VControl>
          <VControl
            raw
            subcontrol
          >
            <VCheckbox
              v-model="options"
              :true-value="{ name: 'option2', label: 'Option 2' }"
              label="線上簽核"
              color="primary"
              solid
            />
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="待簽核"
                color="primary"
                solid
              />
            </VControl>
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="簽核記錄查詢"
                color="primary"
                solid
              />
            </VControl>
          </VControl>
          <VControl
            raw
            subcontrol
          >
            <VCheckbox
              v-model="options"
              :true-value="{ name: 'option2', label: 'Option 2' }"
              label="簽核單流程設定"
              color="primary"
              solid
            />
            <VControl
              raw
              subcontrol
              class="ml-5"
            >
              <VCheckbox
                v-model="options"
                :true-value="{ name: 'option2', label: 'Option 2' }"
                label="簽核單流程查詢"
                color="primary"
                solid
              />
            </VControl>
          </VControl>
        </VField>
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
</style>
