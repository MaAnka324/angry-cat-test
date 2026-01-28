<template>
  <AppHeader />

  <main>
    <HeroSection />
    <StatsCard />
  </main>
</template>

<script setup>
import AppHeader from '@/components/layout/AppHeader.vue'
import HeroSection from '@/components/hero/HeroSection.vue'
import StatsCard from '@/components/stats/StatsCard.vue'
</script>
