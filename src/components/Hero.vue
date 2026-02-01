<template>
  <section class="hero">
    <div class="hero-content">
      <h1 class="hero-title">{{ report.title }}</h1>
      <h2 class="hero-subtitle">{{ report.subtitle }}</h2>
      
      <div class="hero-info">
        <div class="info-item">
          <span class="info-label">Tác Giả:</span>
          <span class="info-value">{{ report.author }}</span>
        </div>
        <div class="info-item">
          <span class="info-label">Ngày:</span>
          <span class="info-value">{{ report.date }}</span>
        </div>
      </div>

      <div class="hero-subject">
        <h3>Đối tượng nghiên cứu</h3>
        <p>{{ report.subject }}</p>
      </div>

      <div class="scroll-indicator">
        <span>Cuộn xuống để xem chi tiết</span>
        <div class="arrow">↓</div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  report: Object
})
</script>

<style scoped>
.hero {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 60px 20px;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  width: 400px;
  height: 400px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  top: -100px;
  right: -100px;
  animation: float 6s ease-in-out infinite;
}

.hero::after {
  content: '';
  position: absolute;
  width: 300px;
  height: 300px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 50%;
  bottom: -50px;
  left: -50px;
  animation: float 8s ease-in-out infinite reverse;
}

@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(30px); }
}

.hero-content {
  max-width: 900px;
  text-align: center;
  position: relative;
  z-index: 1;
  animation: fadeInUp 0.8s ease-out;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero-title {
  font-size: 48px;
  font-weight: 800;
  margin-bottom: 20px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
  letter-spacing: 1px;
}

.hero-subtitle {
  font-size: 24px;
  font-weight: 300;
  margin-bottom: 40px;
  line-height: 1.6;
  opacity: 0.95;
}

.hero-info {
  display: flex;
  justify-content: center;
  gap: 60px;
  margin: 40px 0;
  flex-wrap: wrap;
}

.info-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
}

.info-label {
  font-size: 14px;
  opacity: 0.8;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.info-value {
  font-size: 18px;
  font-weight: 600;
}

.hero-subject {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  padding: 30px;
  border-radius: 12px;
  margin: 40px 0;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.hero-subject h3 {
  font-size: 18px;
  margin-bottom: 12px;
  font-weight: 600;
}

.hero-subject p {
  font-size: 16px;
  line-height: 1.6;
  opacity: 0.95;
}

.scroll-indicator {
  position: absolute;
  bottom: 40px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  font-size: 14px;
  opacity: 0.7;
}

.arrow {
  font-size: 24px;
  animation: bounce-down 1.5s infinite;
}

@keyframes bounce-down {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(10px); }
}

@media (max-width: 768px) {
  .hero {
    min-height: 80vh;
    padding: 40px 20px;
  }

  .hero-title {
    font-size: 32px;
  }

  .hero-subtitle {
    font-size: 18px;
  }

  .hero-info {
    gap: 30px;
  }

  .info-value {
    font-size: 16px;
  }
}
</style>
