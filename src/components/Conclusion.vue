<template>
  <section class="conclusion">
    <div class="conclusion-container">
      <div class="section-header">
        <h2 class="section-title">KẾT LUẬN</h2>
      </div>

      <div class="conclusion-content">
        <p class="conclusion-intro">Mẫu bàn phím "Foam-Cardboard Mod" là một bước đi đột phá trong việc tối ưu hóa chi phí nhưng vẫn đạt được hiệu năng âm thanh cao cấp.</p>

        <div class="conclusion-grid">
          <div class="conclusion-card advantages">
            <h3>✓ Ưu Điểm</h3>
            <ul>
              <li>Khối lượng siêu nhẹ</li>
              <li>Khả năng tiêu âm tuyệt đối</li>
              <li>Chi phí sản xuất thấp</li>
              <li>Tùy biến cao</li>
            </ul>
          </div>

          <div class="conclusion-card limitations">
            <h3>⚠ Hạn Chế</h3>
            <ul>
              <li>Độ bền vật liệu theo thời gian cần nghiên cứu thêm</li>
              <li>Cần các lớp phủ bảo vệ bề mặt</li>
              <li>Nhạy cảm với ẩm độ</li>
              <li>Yêu cầu bảo trì định kỳ</li>
            </ul>
          </div>
        </div>

        <div class="conclusion-recommendation">
          <h3>💡 Khuyến Nghị</h3>
          <p>Đây là mô hình lý tưởng cho các môi trường làm việc yêu cầu sự yên tĩnh tuyệt đối hoặc dành cho những người dùng ưu tiên cảm giác gõ "Thocky" ở dải tần thấp.</p>
        </div>

        <div class="footer-note">
          <p><strong>Tài liệu này thuộc quyền sở hữu của người dùng, được biên soạn cho mục đích nghiên cứu và giải trí.</strong></p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.conclusion {
  margin: 80px 0;
  padding: 60px 40px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border-radius: 16px;
  box-shadow: 0 12px 40px rgba(102, 126, 234, 0.3);
}

.conclusion-container {
  max-width: 900px;
  margin: 0 auto;
}

.section-header {
  margin-bottom: 40px;
  text-align: center;
}

.section-title {
  font-size: 36px;
  font-weight: 800;
  margin: 0;
  letter-spacing: 1px;
}

.conclusion-intro {
  font-size: 18px;
  line-height: 1.7;
  text-align: center;
  margin-bottom: 40px;
  opacity: 0.95;
}

.conclusion-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
  margin: 40px 0;
}

.conclusion-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  padding: 30px;
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s ease;
}

.conclusion-card:hover {
  background: rgba(255, 255, 255, 0.15);
  transform: translateY(-5px);
}

.conclusion-card h3 {
  font-size: 20px;
  font-weight: 700;
  margin: 0 0 20px 0;
}

.conclusion-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.conclusion-card li {
  font-size: 15px;
  line-height: 2;
  padding-left: 20px;
  position: relative;
}

.conclusion-card li::before {
  content: '•';
  position: absolute;
  left: 0;
}

.advantages h3::before {
  content: '✓ ';
}

.limitations h3::before {
  content: '⚠ ';
}

.conclusion-recommendation {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  padding: 30px;
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  margin: 30px 0;
}

.conclusion-recommendation h3 {
  font-size: 20px;
  font-weight: 700;
  margin: 0 0 15px 0;
}

.conclusion-recommendation p {
  font-size: 16px;
  line-height: 1.7;
  margin: 0;
  opacity: 0.95;
}

.footer-note {
  text-align: center;
  padding: 40px 0;
  border-top: 1px solid rgba(255, 255, 255, 0.2);
  margin-top: 40px;
  font-size: 14px;
  opacity: 0.8;
}

@media (max-width: 768px) {
  .conclusion {
    padding: 40px 20px;
    margin: 40px 0;
  }

  .section-title {
    font-size: 28px;
  }

  .conclusion-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }

  .conclusion-card,
  .conclusion-recommendation {
    padding: 20px;
  }

  .conclusion-intro {
    font-size: 16px;
  }
}
</style>
