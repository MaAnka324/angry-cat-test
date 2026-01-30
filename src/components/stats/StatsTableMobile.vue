<template>
  <div class="mobile-table">
    <div v-for="(row, i) in rows" :key="i" class="mobile-table__card">
      <div class="mobile-table__row">
        <span class="mobile-table__label">Дні стейкінгу:</span>
        <span>{{ row.days }} днів</span>
      </div>
      <div class="mobile-table__row">
        <span class="mobile-table__label">Дохід за день:</span>
        <span>{{ row.daily }}</span>
      </div>
      <div class="mobile-table__row">
        <span class="mobile-table__label">Дохід за період:</span>
        <span>{{ row.total }}</span>
      </div>
      <div class="mobile-table__row">
        <span class="mobile-table__label">Очікується:</span>
        <span>{{ row.expected }}</span>
      </div>
      <div class="mobile-table__row">
        <span class="mobile-table__label">Статус:</span>
        <StatusBadge
          :status="row.status"
          :text="row.status === 'active' ? 'Активний' : 'Неактивний'"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import StatusBadge from '@/components/ui/StatusBadge.vue'

defineProps({
  rows: Array
})
</script>

<style scoped>
.mobile-table {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.mobile-table__card {
  background: #fff;
  padding: 16px 5px;
}

.mobile-table__card + .mobile-table__card {
  border-top: 1px solid #ececec;
  margin-top: 0;
}
.mobile-table__row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 1rem;
  color: #222;
  padding: 6px 0;
}
.mobile-table__label {
  color: #888;
  margin-right: 8px;
}
</style>
