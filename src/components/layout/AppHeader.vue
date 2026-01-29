<template>
  <header class="header">
    <div class="header__container">
      <div class="logo">
        <span class="logo-black">C</span>
        <span class="logo-yellow">A</span>
        <span class="logo-yellow">n</span>
        <span class="logo-cat">
          🐱
        </span>
        <span class="logo-yellow">g</span>
        <span class="logo-yellow">r</span>
        <span class="logo-yellow">y</span>
        <span class="logo-black">T</span>
      </div>
      <div class="header-actions">
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
  </header>
</template>

<script setup></script>

<style scoped>

.header {
  width: 100%;
  padding: 0;
  background: transparent;
}

.header__container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
  padding: 32px 0 24px 0;
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
.logo-cat {
  font-size: 1.3em;
  margin: 0 0.05em;
  vertical-align: middle;
}

.header-actions {
  display: flex;
  align-items: center;
  gap: 16px;
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
