<script setup>
import StatsTable from './StatsTable.vue'
import binIcon from '@/assets/icons/bin.svg'
import warningIcon from '@/assets/icons/warning.svg'
import StatsTableMobile from './StatsTableMobile.vue'

import { ref, onMounted, onUnmounted } from 'vue'

const isMobile = ref(false)

function checkMobile() {
  isMobile.value = window.innerWidth < 600
}

onMounted(() => {
  checkMobile()
  window.addEventListener('resize', checkMobile)
})
onUnmounted(() => {
  window.removeEventListener('resize', checkMobile)
})

const rows = [
  { days: 17, daily: '0.5%', total: '31.7%', expected: '10 BIN', status: 'active' },
  { days: 17, daily: '0.5%', total: '31.7%', expected: '10 BIN', status: 'inactive' },
  { days: 17, daily: '0.5%', total: '31.7%', expected: '10 BIN', status: 'active' },
]
</script>

<template>
  <section class="card">
    <div class="card__grid">
      <div class="card__main">
        <div class="card__label">Всього застекано</div>
        <div class="card__total">
          <img :src="binIcon" class="icon" />
          <span class="card__total-value">25 BIN</span>
        </div>
        <div class="card__warning">
          <img :src="warningIcon" class="warning-icon" />
          <span>Максимальний дохід по стейкінгу 200%</span>
        </div>
      </div>
      <div class="card__info">
        <div class="info-row">
          <span>Ребондіровано</span>
          <span>10 BIN</span>
        </div>
        <div class="info-divider"></div>
        <div class="info-row">
          <span>Продано BIN</span>
          <span>360 BIN</span>
        </div>
        <div class="info-divider"></div>
        <div class="info-row">
          <span>Заклеймено BIN</span>
          <span>7660 BIN</span>
        </div>
      </div>
    </div>
    <div class="card__table">
      <component :is="isMobile ? StatsTableMobile : StatsTable" :rows="rows" />
    </div>
  </section>
</template>

<style scoped>
.card {
  background: #fff;
  border-radius: 20px;
  padding: 32px 32px 24px 32px;
  max-width: 900px;
  margin: 0 auto;
  border: 1px solid #E6E6E6;
}

@media (max-width: 600px) {
  .card {
    padding: 16px 8px 16px 8px;
    border-radius: 12px;
    max-width: 100%;
    margin: 0 10px 16px 10px;
  }
  .card__grid {
    flex-direction: column;
    gap: 12px;
    margin-bottom: 18px;
  }
  .card__main {
    min-width: 0;
  }
  .card__label {
    font-size: 1rem;
    margin-bottom: 8px;
  }
  .card__total {
    gap: 12px;
    margin-bottom: 12px;
  }
  .card__total-value {
    font-size: 2rem;
    line-height: 2.2rem;
  }
  .card__warning {
    font-size: 0.95rem;
    gap: 6px;
  }
  .warning-icon {
    width: 16px;
    height: 16px;
  }
  .card__info {
    padding-left: 0;
    border-left: none;
    border-top: 1px solid #ececec;
    padding-top: 12px;
    min-width: 0;
  }
  .info-row {
    font-size: 1rem;
    padding: 12px 0 12px 0;
  }
  .card__table {
    margin-top: 8px;
  }
}


.card__grid {
  display: flex;
  gap: 32px;
  margin-bottom: 32px;
}
.card__main {
  flex: 1 1 0;
  min-width: 220px;
}
.card__label {
  color: #888;
  font-size: 1.1rem;
  margin-bottom: 12px;
}
.card__total {
  display: flex;
  align-items: center;
  gap: 18px;
  margin-bottom: 18px;
}

.icon {
  width: 64px;
  height: 64  px;
}
.card__total-value {
  font-family: 'Manrope', sans-serif;
  font-weight: 700;
  font-size: 52px;
  line-height: 62px;
  letter-spacing: 0px;
  color: #222;
}
.card__warning {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #f5a623;
  font-size: 1rem;
  margin-bottom: 0;
}
.card__warning span {
  color: rgba(34, 34, 34, 0.5);
}
.warning-icon {
  width: 20px;
  height: 20px;
}
.card__info {
  flex: 1 1 0;
  min-width: 220px;
  display: flex;
  flex-direction: column;
  gap: 0;
  justify-content: flex-start;
  padding-left: 32px;
}
.info-row {
  display: flex;
  justify-content: space-between;
  font-size: 1.15rem;
  color: #222;
  padding: 18px 0 18px 0;
}
.info-divider {
  width: 100%;
  height: 1px;
  border-top: 1px solid #ececec;
  margin: 0;
}
.card__table {
  margin-top: 8px;
}

@media (max-width: 900px) {
  .card__grid {
    flex-direction: column;
    gap: 18px;
  }
  .card__info {
    border-left: none;
    padding-left: 0;
    border-top: 1.5px solid #ececec;
    padding-top: 18px;
  }
}
</style>
