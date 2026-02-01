<template>
  <header class="header">
    <div class="header-content">
      <div class="logo">
        <span class="logo-icon">⌨️</span>
        <span class="logo-text">Keyboard Research</span>
      </div>
      <nav class="nav">
        <a href="#abstract" class="nav-link">Tóm Tắt</a>
        <a href="#setup" class="nav-link">Thí Nghiệm</a>
        <a href="#analysis" class="nav-link">Phân Tích</a>
        <a href="#results" class="nav-link">Kết Quả</a>
      </nav>
    </div>
  </header>
</template>

<script setup>
defineProps({
  report: Object
})
</script>

<style scoped>
.header {
  background: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
  color: white;
  padding: 20px 0;
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.header-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 24px;
  font-weight: bold;
  letter-spacing: 1px;
}

.logo-icon {
  font-size: 32px;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-5px); }
}

.logo-text {
  background: linear-gradient(135deg, #3498db, #2ecc71);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.nav {
  display: flex;
  gap: 30px;
}

.nav-link {
  color: #ecf0f1;
  text-decoration: none;
  font-size: 14px;
  font-weight: 500;
  transition: all 0.3s ease;
  padding: 8px 12px;
  border-radius: 4px;
}

.nav-link:hover {
  color: #3498db;
  background: rgba(52, 152, 219, 0.1);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .header-content {
    flex-direction: column;
    gap: 20px;
  }

  .nav {
    gap: 15px;
    font-size: 12px;
  }
}
</style>
