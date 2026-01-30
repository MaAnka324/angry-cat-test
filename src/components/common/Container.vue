<template>
	<div class="container-bg">
		<div class="container">
			<AppHeader />
			<HeroSection />
		</div>
	</div>
</template>

<script setup>
import AppHeader from '@/components/layout/AppHeader.vue'
import HeroSection from '@/components/hero/HeroSection.vue'
</script>

<style scoped>
.container-bg {
	width: 100%;
	background-image: url('@/assets/images/bg-pattern.svg');
	background-repeat: no-repeat;
	background-position: top center;
	background-size: cover;
	margin-bottom: 40px;
}
.container {
	width: 100%;
	max-width: 1100px;
	margin: 0 auto;
	padding: 32px 24px 24px 24px;
	box-sizing: border-box;
}
</style>
