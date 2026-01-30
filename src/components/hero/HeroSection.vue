<template>
  <section class="hero">
    <div class="hero__content">
      <div class="hero__text">
        <h1>
          Hi! It seems I`m <span class="highlight">kindness</span>
        </h1>
        <p class="hero__subtitle">but who knows</p>
        <BaseButton class="hero__button">
          Let’s meet <span class="arrow">→</span>
        </BaseButton>
      </div>
      <div class="hero__image-wrap">
        <img :src="catImage" alt="cat" class="hero__image" />
      </div>
    </div>
  </section>
</template>

<script setup>
import BaseButton from '@/components/ui/BaseButton.vue'
import catImage from '@/assets/images/cat.png'
</script>

<style scoped>
.hero__content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
  padding: 60px 0 40px 0;
}

.hero__text {
  flex: 1 1 0;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  min-width: 320px;
  max-width: 480px;
}

.hero__text h1 {
  font-size: 3rem;
  font-weight: 700;
  line-height: 1.1;
  color: #222;
  margin-bottom: 12px;
}

.highlight {
  color: #f5b400;
  font-weight: 700;
}

.hero__subtitle {
  color: #888;
  font-size: 1.25rem;
  margin-bottom: 32px;
  margin-top: 0;
}

.hero__button {
  background: #fff;
  color: #222;
  font-size: 1.15rem;
  font-weight: 500;
  border-radius: 32px;
  box-shadow: 0 4px 16px 0 rgba(34,34,34,0.10);
  padding: 14px 36px 14px 28px;
  border: none;
  transition: box-shadow 0.2s;
  display: flex;
  align-items: center;
  gap: 8px;
}
.hero__button:hover {
  box-shadow: 0 8px 24px 0 rgba(34,34,34,0.13);
}
.arrow {
  font-size: 1.2em;
  margin-left: 4px;
}

.hero__image-wrap {
  flex: 1 1 0;
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 360px;
}

.hero__image {
  width: 360px;
  height: 360px;
  object-fit: contain;
  display: block;
}

@media (max-width: 900px) {
  .hero__content {
    flex-direction: column;
    gap: 32px;
    padding: 40px 0 24px 0;
  }
  .hero__image-wrap {
    min-width: 0;
  }
}
</style>
