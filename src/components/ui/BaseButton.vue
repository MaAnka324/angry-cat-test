<template>
  <button class="btn">
    <slot />
  </button>
</template>

<style scoped>
.btn {
  padding: 14px 32px;
  border-radius: 999px;
  background: white;
  border: none;
  font-weight: 600;
  cursor: pointer;
}
</style>
