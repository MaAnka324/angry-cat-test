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
  border-collapse: collapse;
}

th, td {
  padding: 12px;
  text-align: left;
}
</style>
