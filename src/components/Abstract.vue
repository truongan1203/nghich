<template>
  <section id="abstract" class="abstract">
    <div class="abstract-container">
      <div class="section-header">
        <div class="section-number">01</div>
        <h2 class="section-title">{{ report.title }}</h2>
      </div>

      <div class="abstract-content">
        <div class="abstract-text">
          <p>{{ report.subtitle }}</p>
        </div>
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
.abstract {
  margin: 80px 0;
  padding: 60px 40px;
  background: white;
  border-radius: 16px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
  position: relative;
  overflow: hidden;
}

.abstract::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #667eea, #764ba2, #f093fb);
}

.abstract-container {
  max-width: 900px;
  margin: 0 auto;
}

.section-header {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 40px;
}

.section-number {
  font-size: 48px;
  font-weight: 800;
  color: #667eea;
  opacity: 0.3;
}

.section-title {
  font-size: 28px;
  font-weight: 700;
  color: #2c3e50;
  margin: 0;
}

.abstract-content {
  margin-top: 30px;
}

.abstract-text {
  font-size: 16px;
  line-height: 1.8;
  color: #555;
  text-align: justify;
}

.abstract-text p {
  margin: 0;
  color: #666;
}

@media (max-width: 768px) {
  .abstract {
    padding: 40px 20px;
    margin: 40px 0;
  }

  .section-number {
    font-size: 36px;
  }

  .section-title {
    font-size: 22px;
  }

  .abstract-text {
    font-size: 15px;
    text-align: left;
  }
}
</style>
