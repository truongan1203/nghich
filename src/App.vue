<script setup>
import { ref } from 'vue'
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Abstract from './components/Abstract.vue'
import Section from './components/Section.vue'
import Conclusion from './components/Conclusion.vue'

const reportData = {
  title: "BÁO CÁO NGHIÊN CỨU KỸ THUẬT",
  subtitle: "TỐI ƯU HÓA HÌNH THÁI ÂM HỌC VÀ TRẢI NGHIỆM XÚC GIÁC TRÊN HỆ THỐNG CẤU TRÚC VẬT LIỆU TỔNG HỢP SIÊU NHẸ (FOAM-CARDBOARD COMPOSITE)",
  author: "Khổng Phú Tử",
  date: "02/02/2026",
  subject: "Thiết bị nhập liệu cơ học tùy chỉnh (Custom Mechanical Keyboard) - Phiên bản thử nghiệm Type-S / HHKB Mod"
}

const sections = ref([
  {
    id: 'abstract',
    title: 'TÓM TẮT (ABSTRACT)',
    content: 'Nghiên cứu này trình bày việc thiết kế và đánh giá một mẫu bàn phím cơ độc bản, tập trung vào việc triệt tiêu cộng hưởng âm thanh thông qua các vật liệu có mật độ thấp. Khác với các tiêu chuẩn công nghiệp sử dụng nhôm (Aluminum) hay nhựa cứng (Polycarbonate), đối tượng nghiên cứu sử dụng hệ khung vỏ từ Polystyrene (xốp) và Cellulose (bìa các-tông). Kết quả cho thấy sự kết hợp giữa switch Silent Tactile và khung vỏ hấp thụ xung lực tạo ra một profile âm thanh "Ultra-Silent" mà các vật liệu truyền thống khó đạt được.'
  },
  {
    id: 'setup',
    title: 'THIẾT LẬP THỰC NGHIỆM (EXPERIMENTAL SETUP)',
    subsections: [
      {
        title: 'Cấu trúc khung vỏ (The Chassis)',
        content: '<strong>Đế (Lower Case):</strong> Polystyrene mật độ trung bình (xốp trắng), độ dày xấp xỉ 20mm, đóng vai trò là buồng tiêu âm thứ cấp.<br><strong>Bề mặt (Top Case):</strong> Cellulose gia cố (bìa cát-tông) kết hợp với màng liên kết sợi giấy (băng dính giấy), tạo cấu trúc bán cứng (semi-rigid).'
      },
      {
        title: 'Linh kiện điều khiển và truyền động',
        content: '<strong>Switch (Bộ truyền động):</strong> Haimu x Geon HG Yellow Silent Tactile. Không sử dụng đệm silicon, tận dụng thiết kế chân switch co giãn để giảm chấn.<br><strong>Keycap (Bề mặt tiếp xúc):</strong> JKDK Gray & White. Profile: Cherry/OEM (tối ưu hóa diện tích tiếp xúc đầu ngón tay).<br><strong>Stabilizer (Bộ ổn định):</strong> Cherry PCB Mount, được tinh chỉnh để giảm thiểu ma sát cơ học.'
      }
    ]
  },
  {
    id: 'analysis',
    title: 'PHÂN TÍCH VẬT LIỆU VÀ CƠ CHẾ ÂM HỌC',
    subsections: [
      {
        title: 'Hệ số hấp thụ âm thanh của vật liệu xốp',
        content: 'Theo lý thuyết sóng âm, các vật liệu có cấu trúc lỗ rỗng (porous materials) như Polystyrene có khả năng biến đổi năng lượng âm thanh thành nhiệt năng thông qua ma sát trong các lỗ siêu nhỏ. Kết quả: Hiện tượng "Case Ping" (tiếng vang trong vỏ) bị triệt tiêu hoàn toàn (giá trị xấp xỉ 0dB).'
      },
      {
        title: 'Cấu trúc Gasket "Dã chiến"',
        content: 'Lớp băng dính giấy không chỉ đóng vai trò thẩm mỹ mà còn tạo ra một lớp đệm đàn hồi giữa Topcase và Plate. Điều này tạo ra hiệu ứng "Bounce" (độ nhún) tương tự như các hệ thống Gasket Mount cao cấp, giúp giảm áp lực lên đầu ngón tay khi gõ liên tục trong thời gian dài.'
      }
    ]
  },
  {
    id: 'results',
    title: 'KẾT QUẢ VÀ THẢO LUẬN',
    subsections: [
      {
        title: 'Đặc tính xúc giác (Tactile Feel)',
        content: 'Switch HG Yellow cung cấp một khấc (bump) rõ nét nhưng tĩnh lặng. Khi kết hợp với nền tảng vỏ xốp, điểm chạm đáy (bottom-out) trở nên "mềm" hơn, tạo ra cảm giác gõ tương tự như các dòng bàn phím màng điện dung (Topre) huyền thoại nhưng với độ tùy biến cao hơn.'
      },
      {
        title: 'Thẩm mỹ học chức năng (Functional Aesthetics)',
        content: 'Diện mạo của thiết bị mang đậm triết lý DIY Brutalism. Việc ghi chú thủ công bằng bút mực (Type-S, HHKB Pro 2) thể hiện xu hướng cá nhân hóa tối đa, đồng thời là lời khẳng định về công năng vượt lên trên hình thức bề ngoài.'
      }
    ]
  }
])
</script>

<template>
  <div class="app">
    <Header :report="reportData" />
    <Hero :report="reportData" />
    
    <main class="main-content">
      <Abstract :report="reportData" />
      
      <div class="sections-container">
        <Section 
          v-for="section in sections" 
          :key="section.id"
          :section="section"
        />
      </div>
      
      <Conclusion />
    </main>
  </div>
</template>

<style scoped>
:root {
  --primary-color: #2c3e50;
  --accent-color: #3498db;
  --secondary-color: #ecf0f1;
  --text-color: #2c3e50;
  --light-text: #7f8c8d;
}

.app {
  min-height: 100vh;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
}

.main-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.sections-container {
  display: flex;
  flex-direction: column;
  gap: 40px;
  margin: 60px 0;
}

@media (max-width: 768px) {
  .main-content {
    padding: 0 15px;
  }
  
  .sections-container {
    gap: 30px;
  }
}
</style>
