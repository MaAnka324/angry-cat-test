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
  padding: 6px 14px;
  border-radius: 12px;
  font-size: 12px;
}

.active {
  background: #dff9ef;
  color: #1ca37c;
}

.inactive {
  background: #ffe3e3;
  color: #ff4d4f;
}
</style>
