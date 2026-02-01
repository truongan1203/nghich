<template>
  <section :id="section.id" class="section">
    <div class="section-container">
      <div class="section-header">
        <h2 class="section-title">{{ section.title }}</h2>
      </div>

      <div class="section-body">
        <!-- If section has direct content -->
        <p v-if="section.content && !section.subsections" class="section-text">
          {{ section.content }}
        </p>

        <!-- If section has subsections -->
        <div v-if="section.subsections" class="subsections">
          <div v-for="(subsection, index) in section.subsections" :key="index" class="subsection">
            <h3 class="subsection-title">{{ subsection.title }}</h3>
            <p class="subsection-text" v-html="subsection.content"></p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  section: Object
})
</script>

<style scoped>
.section {
  margin: 60px 0;
  padding: 60px 40px;
  background: white;
  border-radius: 12px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.section:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.12);
}

.section-container {
  max-width: 900px;
  margin: 0 auto;
}

.section-header {
  margin-bottom: 40px;
  padding-bottom: 20px;
  border-bottom: 3px solid #667eea;
}

.section-title {
  font-size: 28px;
  font-weight: 700;
  color: #2c3e50;
  margin: 0;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.section-text {
  font-size: 16px;
  line-height: 1.8;
  color: #555;
  text-align: justify;
  margin: 0;
}

.subsections {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.subsection {
  padding: 25px;
  background: linear-gradient(135deg, #f5f7fa 0%, #ecf0f1 100%);
  border-radius: 8px;
  border-left: 4px solid #3498db;
  transition: all 0.3s ease;
}

.subsection:hover {
  background: linear-gradient(135deg, #ecf0f1 0%, #e8eef5 100%);
  transform: translateX(5px);
}

.subsection-title {
  font-size: 18px;
  font-weight: 700;
  color: #2c3e50;
  margin: 0 0 12px 0;
  text-transform: capitalize;
}

.subsection-text {
  font-size: 15px;
  line-height: 1.7;
  color: #666;
  margin: 0;
  text-align: justify;
}

@media (max-width: 768px) {
  .section {
    padding: 40px 20px;
    margin: 30px 0;
  }

  .section-title {
    font-size: 22px;
  }

  .section-text,
  .subsection-text {
    font-size: 15px;
    text-align: left;
  }

  .subsection {
    padding: 20px;
  }

  .subsection-title {
    font-size: 16px;
  }
}
</style>
