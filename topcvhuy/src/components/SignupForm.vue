<template>
  <nav>
    <div class="nav-img">
      <img src="../assets/image/logohce.png" alt="" />
    </div>
    <div class="nav-content">
      <div class="nav-left">
        <ul>
          <li>
            Việc làm
          </li>
          <li>Hồ sơ & CV</li>
          <li>Công cụ</li>
          <li><router-link to="/" class="login-link">Trang chủ</router-link></li>
        </ul>
      </div>
      <div class="nav-right">
        <div class="icon"><i class="fa-solid fa-bell"></i></div>
        
        <div class="icon"><i class="fa-solid fa-message"></i></div>
        <div class="info-user">
          <div class="avatar">
            <div class="icon">
              <router-link to="/login" class="icon">
                <i class="fa-solid fa-user"></i>
              </router-link>
            </div>
          </div>
          <div class="name">Nguyễn Văn A </div>
        </div>
      </div>
    </div>
  </nav>

  <form>
    <div class="wrapper"> 
      <div class="form-signup">
        <h2>Đăng ký</h2>
        <div class="input-group">
          
          <input type="text" v-model="newUsername" required>
          <label for="newUsername">Tên đăng nhập mới</label>
        </div>
        <div class="input-group">
          
          <input type="email" v-model="newEmail" required>
          <label for="newEmail">Email</label>
        </div>
        <div class="input-group">
          
          <input type="password" v-model="newPassword" required>
          <label for="newPassword">Mật khẩu mới</label>
        </div>
        <div class="Agree">
          <input type="checkbox" v-model="agree" id="Agree">
          <label for="Agree">Tôi đồng ý với các điều khoán và tiếp tục</label>
        </div>
        <button class="btnLogin" type="button" @click="signup">Đăng ký</button>
        <div class="signupLink">
          <p>Bạn đã có tài khoản <router-link to="/login" class="login-link">Đăng Nhập</router-link></p>
        </div>
      </div>
    </div>
  </form>
</template>

<script>
import { ref } from "vue";
import '/src/assets/css/signup.css';
export default {
  setup() {
    const newUsername = ref('');
    const newEmail = ref('');
    const newPassword = ref('');
    const agree = ref(false);

    function onSubmit() {
      console.log({ newUsername: newUsername.value, newEmail: newEmail.value, newPassword: newPassword.value });
    }

    const signup = () => {
      if (newUsername.value === '' || newEmail.value === '' || newPassword.value === '' || !agree.value) {
        alert('Vui lòng điền đầy đủ thông tin và đồng ý với các điều khoản.');
      } else {
        alert('Đăng ký thành công. Bạn có thể sử dụng tài khoản mới để đăng nhập.');
      }
    };

    const showLoginForm = () => {
      // Xử lý khi click vào link Đăng Nhập
    };

    return { newUsername, newEmail, newPassword, agree, onSubmit, signup, showLoginForm };
  }
};

</script>


<style scoped>

</style>
