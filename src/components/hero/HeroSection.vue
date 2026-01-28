<template>
  <section class="hero">
    <div class="hero__text">
      <h1>
        Hi! It seems I'm
        <span class="highlight">kindness</span>
      </h1>

      <p>but who knows</p>

      <BaseButton>
        Let’s meet →
      </BaseButton>
    </div>

    <div class="hero__image">
      <img :src="catImage" alt="cat" />
    </div>
  </section>
</template>

<script setup>
import BaseButton from '@/components/ui/BaseButton.vue'
import catImage from '@/assets/images/cat.png'
</script>

<style scoped>
.hero {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 60px 24px;
}

.highlight {
  color: #f5b400;
}
</style>
