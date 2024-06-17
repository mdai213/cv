<template>
  <nav>
    <div class="nav-img">
      <img src="../assets/image/logohce.png" alt="" />
    </div>
    <div class="nav-content">
      <div class="nav-left">
        <details>
          <summary class="menu"><B>MENU</B></summary>
          <ul>
            <li>
              <router-link to="/" class="login-link">Trang chủ</router-link>
            </li>
            <li>Việc làm</li>
            <li>Hồ sơ & CV</li>
            <li>Công cụ</li>
          </ul>
        </details>
      </div>
      <div class="nav-right">
        <div class="icon"><i class="fa-solid fa-bell"></i></div>

        <div class="icon"><i class="fa-solid fa-message"></i></div>
        <div class="info-user">
          <div class="name">
            <div
              class="nav_login"
              @click="showLoginModal = true"
              v-if="!isLoggedIn"
            >
              <p>Đăng Nhập</p>
            </div>
            <div
              class="nav_register"
              @click="showRegisterModal = true"
              v-if="!isLoggedIn"
            >
              <p>Đăng Ký</p>
            </div>
            <div class="nav_register" @click="logout" v-else>
              <div class="avatar">
                <div class="icon">
                  <router-link to="/login" class="icon">
                    <i class="fa-solid fa-user"></i>
                  </router-link>
                </div>
              </div>
              <p class="nav_register_first">{{ loginUsername }}</p>
              <span class="nav_register_mid">|</span>
              <p class="nav_register_last" @click="logout">Logout</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>

  <div class="father">
    <div class="wrapper">
      <div class="sidebar">
        <div class="profile-pic-container">
          <div class="profile-pic">
            <input type="file" class="file-input" />
          </div>
        </div>
        <div class="form-input">
          <input
            class="form-control-lg"
            type="text"
            placeholder="Name"
            aria-label=".form-control-lg example"
          />
          <input
            class="form-control"
            type="text"
            placeholder="Profession"
            aria-label="default input example"
          />
        </div>
        <div class="section-header">
          <h3>THÔNG TIN CÁ NHÂN</h3>
        </div>
        <div class="form-section">
          <form action="" class="form-container">
            <fieldset class="form-fieldset">
              <div class="form-content">
                <div class="form-item">
                  <label for="date" class="text-sm">Date</label>
                  <input id="date" type="text" class="input-field" />
                </div>
                <div class="form-item">
                  <label for="address" class="text-sm">Address</label>
                  <input id="address" type="text" class="input-field" />
                </div>
                <div class="form-item">
                  <label for="email" class="text-sm">Email</label>
                  <input id="email" type="email" class="input-field" />
                </div>
                <div class="form-item">
                  <label for="phone" class="text-sm">Phone</label>
                  <input id="phone" type="text" class="input-field" />
                </div>
                <div class="form-item">
                  <label for="gender" class="text-sm">Gender</label>
                  <input id="gender" type="text" class="input-field" />
                </div>
              </div>
            </fieldset>
          </form>
        </div>
      </div>

      <div class="container">
        <div class="form-section">
          <div class="form-group">
            <label for="career-goals" class="form-label">
              <h4>Mục tiêu nghề nghiệp</h4>
            </label>
            <textarea
              class="form-control"
              id="career-goals"
              rows="3"
              placeholder="Text Here"
            ></textarea>
          </div>
          <div class="form-group">
            <label for="work-experience" class="form-label">
              <h4>Kinh nghiệm làm việc</h4>
            </label>
            <textarea
              class="form-control"
              id="work-experience"
              rows="3"
              placeholder="Text Here"
            ></textarea>
          </div>
          <div class="form-group">
            <label for="education" class="form-label">
              <h4>Học Vấn</h4>
            </label>
            <textarea
              class="form-control"
              id="education"
              rows="3"
              placeholder="Text Here"
            ></textarea>
          </div>
          <div class="form-group">
            <label for="activities" class="form-label">
              <h4>Hoạt động</h4>
            </label>
            <textarea
              class="form-control"
              id="activities"
              rows="3"
              placeholder="Text Here"
            ></textarea>
          </div>
          <div class="form-group">
            <label for="skills" class="form-label">
              <h4>Các kỹ năng</h4>
            </label>
            <textarea
              class="form-control"
              id="skills"
              rows="3"
              placeholder="Text Here"
            ></textarea>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="button-container">
  <button @click="downloadPDF" class="button">Lưu và tải về</button>
</div>
</template>

<script>
import jsPDF from "jspdf";
import html2canvas from "html2canvas";

export default {
  name: "CvForm",
  data() {
    return {
      isLoggedIn: false, // Giả sử bạn có trạng thái đăng nhập
      showLoginModal: false,
      showRegisterModal: false,
      loginUsername: "User", // Giả sử bạn có tên người dùng đăng nhập
    };
  },
  methods: {
    downloadPDF() {
      const element = document.querySelector(".father"); // Chọn phần tử bạn muốn tạo PDF

      html2canvas(element).then((canvas) => {
        const imgData = canvas.toDataURL("image/png");
        const pdf = new jsPDF("p", "mm", "a4");
        const imgProps = pdf.getImageProperties(imgData);
        const pdfWidth = pdf.internal.pageSize.getWidth();
        const pdfHeight = (imgProps.height * pdfWidth) / imgProps.width;

        pdf.addImage(imgData, "PNG", 0, 0, pdfWidth, pdfHeight);
        pdf.save("cv-form.pdf");
      });
    },
    logout() {
      this.isLoggedIn = false; // Thêm logic đăng xuất của bạn ở đây
    },
    created() {
      // Lấy templateId từ route
      this.templateId = this.$route.params.templateId;
    },
    data() {
      return {
        templateId: null,
      };
    },
  },
};
</script>

<style>
@import url(/src/assets/css/cvForm.css);
@import url(/src/assets/css/style.css);
</style>
<style>
.button-container {
  display: flex;
  justify-content: flex-end;
  align-items: flex-start;
  height: 100vh; /* Chiều cao toàn màn hình */
  padding: 0; /* Loại bỏ khoảng đệm để nút sát lên trên */
  margin: 0; /* Đảm bảo không có khoảng cách mặc định */
  
}

.button {
  padding: 15px 30px;
  font-size: 18px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  top: 650px;
  cursor: pointer;
}

.button:hover {
  background-color: #0056b3;
}
</style>