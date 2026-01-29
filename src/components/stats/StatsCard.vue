<script setup>
import StatsTable from './StatsTable.vue'
import binIcon from '@/assets/icons/bin.svg'
import warningIcon from '@/assets/icons/warning.svg'

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
          <span class="card__total-icon-wrap">
            <span class="card__total-bg"><img :src="binIcon" class="icon" /></span>
          </span>
          <span class="card__total-value">25 BIN</span>
        </div>
        <div class="card__warning">
          <img :src="warningIcon" class="warning-icon" />
          <span>Максимальний дохід по стейкінгу 200%</span>
        </div>
      </div>
      <div class="card__info">
        <div class="info-row">
          <span>Ребондировано</span>
          <span>10 BIN</span>
        </div>
        <div class="info-row">
          <span>Продано BIN</span>
          <span>360 BIN</span>
        </div>
        <div class="info-row">
          <span>Заклеймено BIN</span>
          <span>7660 BIN</span>
        </div>
      </div>
    </div>
    <div class="card__table">
      <StatsTable :rows="rows" />
    </div>
  </section>
</template>

<style scoped>
.card {
  background: #fff;
  border-radius: 20px;
  box-shadow: 0 2px 16px 0 rgba(34,34,34,0.06);
  padding: 32px 32px 24px 32px;
  max-width: 900px;
  margin: 0 auto;
  border: 1.5px solid #f3f3f3;
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
.card__total-icon-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
}
.card__total-bg {
  background: #fdf6e3;
  border-radius: 50%;
  width: 56px;
  height: 56px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.icon {
  width: 32px;
  height: 32px;
}
.card__total-value {
  font-size: 2.6rem;
  font-weight: 700;
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
.warning-icon {
  width: 20px;
  height: 20px;
}
.card__info {
  flex: 1 1 0;
  min-width: 220px;
  display: flex;
  flex-direction: column;
  gap: 18px;
  justify-content: flex-start;
  border-left: 1.5px solid #ececec;
  padding-left: 32px;
}
.info-row {
  display: flex;
  justify-content: space-between;
  font-size: 1.15rem;
  color: #222;
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
