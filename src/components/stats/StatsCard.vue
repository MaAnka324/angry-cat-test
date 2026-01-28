<template>
  <section class="card">
    <h2>Всього застейкано</h2>

    <div class="total">
      <strong>25 BIN</strong>
    </div>

    <StatsTable :rows="rows" />
  </section>
</template>

<script setup>
import StatsTable from './StatsTable.vue'

const rows = [
  {
    days: 17,
    daily: '0.5%',
    total: '31.7%',
    expected: '10 BIN',
    status: 'active'
  },
  {
    days: 17,
    daily: '0.5%',
    total: '31.7%',
    expected: '10 BIN',
    status: 'inactive'
  }
]
</script>

<style scoped>
.card {
  background: white;
  border-radius: 24px;
  padding: 32px;
  max-width: 900px;
  margin: 0 auto;
}
</style>
