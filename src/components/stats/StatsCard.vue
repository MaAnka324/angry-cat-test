<script setup>
import StatsTable from './StatsTable.vue'

import binIcon from '@/assets/icons/bin.svg'
import warningIcon from '@/assets/icons/warning.svg'

const rows = [
  {
    days: 17,
    daily: '0.5%',
    total: '31.7%',
    expected: '10 BIN',
    status: 'active'
  },
  {
    days: 10,
    daily: '0.3%',
    total: '15%',
    expected: '5 BIN',
    status: 'inactive'
  }
]
</script>

<template>
  <section class="card">
    <div class="total">
      <img :src="binIcon" class="icon" />
      <span>25 BIN</span>
    </div>

    <div class="warning">
      <img :src="warningIcon" />
      <p>Максимальний дохід по стейкінгу 200%</p>
    </div>

    <StatsTable :rows="rows" />
  </section>
</template>

<style scoped>
.total {
  display: flex;
  align-items: center;
  gap: 12px;
}

.icon {
  width: 32px;
  height: 32px;
}

.warning {
  display: flex;
  gap: 8px;
  color: #f5a623;
  font-size: 14px;
}
</style>
