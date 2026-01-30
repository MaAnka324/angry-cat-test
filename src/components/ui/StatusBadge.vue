<template>
  <span :class="['badge', status]">
    {{ text }}
  </span>
</template>

<script setup>
defineProps({
  status: String,
  text: String
})
</script>

<style scoped>
.badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 96px;
  min-height: 42px;
  padding: 0 16px;
  border-radius: 8px;
  font-size: 1.25rem;
  font-weight: 500;
  box-sizing: border-box;
}

.active {
  background: #87FFDF;
  color: #24A483;
}

.inactive {
  background: #FFDDDB;
  color: #FD2517;
}
</style>
