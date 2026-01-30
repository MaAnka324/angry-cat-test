<template>
  <header class="header">
    <div class="header__container">
      <div class="logo">
        <span class="logo-black">C</span>
        <span class="logo-yellow">A</span>
        <span class="logo-yellow">n</span>
        <span class="logo-yellow logo-g-cat">
          g
          <img src="/src/assets/images/cat2.svg" alt="cat" class="cat-img" />
        </span>
        <span class="logo-yellow">r</span>
        <span class="logo-yellow">y</span>
        <span class="logo-black">T</span>
      </div>
      <!-- Desktop actions -->
      <div class="header-actions desktop-only">
        <div class="wallet-balance capsule">
          <span class="balance-label">Wallet balance:</span>
          <strong class="balance-value">100 BNB</strong>
        </div>
        <div class="wallet-address capsule">
          <span class="address">0x63...B492</span>
          <span class="arrow">▼</span>
        </div>
      </div>
      <!-- Burger icon for mobile -->
      <button class="burger-menu mobile-only" @click="isMenuOpen = !isMenuOpen" aria-label="Open menu">
        <span class="burger-bar"></span>
        <span class="burger-bar"></span>
        <span class="burger-bar"></span>
      </button>
    </div>
    <!-- Mobile menu overlay -->
    <transition name="fade">
      <div v-if="isMenuOpen" class="mobile-menu-overlay" @click.self="isMenuOpen = false">
        <div class="mobile-menu-content">
          <div class="wallet-balance capsule">
            <span class="balance-label">Wallet balance:</span>
            <strong class="balance-value">100 BNB</strong>
          </div>
          <div class="wallet-address capsule">
            <span class="address">0x63...B492</span>
            <span class="arrow">▼</span>
          </div>
        </div>
      </div>
    </transition>
  </header>
</template>

<script setup>
import { ref } from 'vue';
const isMenuOpen = ref(false);
</script>

<style scoped>


.header {
  width: 100%;
  padding: 0;
  background: transparent;
  position: relative;
  z-index: 10;
}

.header__container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  position: relative;
}

.logo {
  display: flex;
  align-items: center;
  font-size: 2.2rem;
  font-weight: 700;
  letter-spacing: 0.02em;
  gap: 0.05em;
}
.logo-black {
  color: #2d2d2d;
}
.logo-yellow {
  color: #eac24b;
}
.logo-g-cat {
  position: relative;
  display: inline-block;
}
.cat-img {
  position: absolute;
  left: 50%;
  top: 80%;
  transform: translate(-50%, -110%);
  width: 7em;
  height: auto;
  pointer-events: none;
  z-index: 2;
}

.header-actions {
  display: flex;
  align-items: center;
  gap: 16px;
}

.desktop-only {
  display: flex;
}
.mobile-only {
  display: none;
}

@media (max-width: 600px) {
  .desktop-only {
    display: none !important;
  }
  .mobile-only {
    display: flex !important;
    background: #fff;
    border-radius: 50%;
    box-shadow: 0 1px 4px 0 rgba(0,0,0,0.08);
    width: 48px;
    height: 48px;
    align-items: center;
    justify-content: center;
    border: none;
    cursor: pointer;
    position: absolute;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
    z-index: 20;
    padding: 0;
  }
  .burger-menu {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 5px;
  }
  .burger-bar {
    display: block;
    width: 24px;
    height: 3px;
    background: #222;
    margin: 0;
    border-radius: 2px;
    transition: all 0.3s;
  }
}

/* Mobile menu overlay */
.mobile-menu-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0,0,0,0.18);
  z-index: 1000;
  display: flex;
  align-items: flex-start;
  justify-content: flex-end;
}
.mobile-menu-content {
  background: #fff;
  border-radius: 0 0 0 24px;
  box-shadow: 0 2px 16px 0 rgba(0,0,0,0.08);
  margin: 16px 12px 0 0;
  padding: 32px 24px 24px 24px;
  min-width: 220px;
  display: flex;
  flex-direction: column;
  gap: 18px;
}

/* Fade transition for overlay */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.2s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}

.capsule {
  display: flex;
  align-items: center;
  background: #fff;
  border-radius: 999px;
  box-shadow: 0 1px 4px 0 rgba(0,0,0,0.04);
  padding: 10px 28px;
  font-size: 1rem;
  min-width: 0;
  border: 1px solid #ececec;
}

.wallet-balance {
  margin-right: 8px;
  gap: 8px;
}
.balance-label {
  color: #888;
  font-size: 1rem;
  margin-right: 4px;
}
.balance-value {
  color: #222;
  font-weight: 700;
  font-size: 1.08rem;
}

.wallet-address {
  gap: 8px;
  background: #f8faf9;
  border: 1px solid #e6f6f0;
}
.address {
  color: #7be3c7;
  font-weight: 500;
  font-size: 1.05rem;
  letter-spacing: 0.01em;
}
.arrow {
  color: #b2e9d7;
  font-size: 1.1em;
  margin-left: 2px;
}
</style>
