<template>
  <table class="table">
    <thead>
      <tr>
        <th>Дні стейкінгу</th>
        <th>Дохід за день</th>
        <th>Дохід за період</th>
        <th>Очікується</th>
        <th>Статус</th>
      </tr>
    </thead>

    <tbody>
      <tr v-for="(row, i) in rows" :key="i">
        <td>{{ row.days }} днів</td>
        <td>{{ row.daily }}</td>
        <td>{{ row.total }}</td>
        <td>{{ row.expected }}</td>
        <td>
          <StatusBadge
            :status="row.status"
            :text="row.status === 'active' ? 'Активний' : 'Неактивний'"
          />
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
import StatusBadge from '@/components/ui/StatusBadge.vue'

defineProps({
  rows: Array
})
</script>

<style scoped>
.table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  background: #fff;
  border-radius: 16px;
  overflow: hidden;
  font-size: 1.08rem;
  margin-top: 0;
}

th {
  color: #888;
  font-weight: 500;
  background: #fff;
  padding: 16px 12px 14px 0;
  border-bottom: 2px solid #f3f3f3;
  text-align: left;
}
td {
  color: #222;
  background: #fff;
  padding: 16px 12px 16px 0;
  border-bottom: 1.5px solid #f3f3f3;
  text-align: left;
}
tr:last-child td {
  border-bottom: none;
}
</style>
