  <template>
    
      <DetailCV v-if="isShow" @my-event="Close"/> 
      <nav>
        <div class="nav-img">
          <img src="../assets/image/logohce.png" alt="" />
        </div>
        <div class="nav-content">
          <div class="nav-left">
            <details  >
              <summary class="menu"   > <B>MENU</B> </summary>
              <ul>
              <li><router-link to="/" class="login-link">Trang chủ</router-link></li>
              <li>
                Việc làm
              </li>
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
                <div class="nav_login"  @click="showLoginModal = true" v-if="!isLoggedIn">
            <p >Đăng Nhập</p>
          </div>
          <div class="nav_register" @click="showRegisterModal = true" v-if="!isLoggedIn">
            <p>Đăng Ký </p>
          </div>
          <div class="nav_register" @click="logout" v-else>
            <div class="avatar">
                <div class="icon">
                  
                  <router-link to="/login" class="icon" >
                    <i class="fa-solid fa-user"></i>
                  </router-link>
                  
                </div>
              </div>
            <p class="nav_register_first">{{ loginUsername }}</p>
            <span class="nav_register_mid">|</span>
            <div>
              <button @click="logout">Đăng xuất</button>
            </div>
            
          </div>
          </div>
                </div>
            </div>
          </div>
      </nav>




      <main>
        <div class="top-banner">
          <div class="top-banner-content">
            <div class="top-banner-content-detail">
              <h1 class="title">
                Danh sách mẫu CV xin việc
                <br />
                tiếng Việt <img src="../assets/image/vn.png" alt="" /> / Anh
                <img src="../assets/image/us.png" alt="">/ Nhật
                <img src="../assets/image/jp.png" /> chuẩn 2024
              </h1>
              <p class="caption">
                Các mẫu CV được thiết kế chuẩn theo từng ngành nghề.
                <br />

                Phù hợp với cả sinh viên và người đi làm.
              </p>
            </div>
          </div>
        </div>

        <div class="main-container">
          <div class="box-version-tab">
            <ul class="cv">
              <li class="active">Mẫu CV theo Style</li>
            </ul>
          </div>
        

  <!-- thay đổi chỗ này thành những mẫu khác nhau -->
  <div class="list-item">
    <div id="list-cv-style">
      <div class="row">
        <div class="col-md-3 col-sm-4 list-cv-style_item">
          <div class="template-cv-item box-shadow">
            <div class="cv-img">
              <div class="cv-img-tag">
                <div class="cv-img-tag_item tag-ver2">
                  <i class="fa-solid fa-bolt-lightning"></i> Powered by CV Builder 2.0
                </div>
              </div>
              <img src="https://www.topcv.vn/images/cv/screenshots/thumbs/cv-template-thumbnails-v1.2/delicate_2_v2.png?v=1.0.6" alt="Mẫu CV tiếng Việt" title="Mẫu CV tiếng Việt" width="450" height="500" class="img-responsive lazy">
              <div class="cv-overlay">
                <a class="chooseCvData btn-use-now">
                  <span class="create-cv-button">
                    <router-link to="cv" class="">Dùng mẫu</router-link>
                  </span>
                </a>
                <a @click="showDialog" href="javascript:void(0)" class="btn-preview preview-cv-template-button">
                  <span class="preview-button">
                    <i class="fa-solid fa-eye"></i> Xem trước
                  </span>
                </a>
              </div>
              <div class="clearfix"></div>
            </div>
            <div class="template-cv-item_info">
              <div class="tag-list">
                Chuyên nghiệp
                Đơn giản
                <a href="javascript:void(0)" class="template-cv-item-tag">+8</a>
              </div>
              <div class="template-cv-title">
                <h2>Mẫu 1 </h2>
              </div>
            </div>
          </div>
        </div>


        <div class="col-md-3 col-sm-4 list-cv-style_item">
        <div class="template-cv-item box-shadow">
            <div class="cv-img">
              <div class="cv-img-tag">
                <div class="cv-img-tag_item tag-ver2">
                  <i class="fa-solid fa-bolt-lightning"></i> Powered by CV Builder 2.0
                </div>
              </div>
              <img src="https://www.topcv.vn/images/cv/screenshots/thumbs/cv-template-thumbnails-v1.2/premium_v2.png?v=1.0.6" alt="Mẫu CV tiếng Việt" title="Mẫu CV tiếng Việt" width="450" height="500" class="img-responsive lazy">
              <div class="cv-overlay">
                <a class="chooseCvData btn-use-now">
                  <span class="create-cv-button">
                    <router-link to="cv" class="">Dùng mẫu</router-link>
                    
                  </span>
                </a>
                <a @click="showDialog" href="javascript:void(0)" class="btn-preview preview-cv-template-button">
                  <span class="preview-button">
                    <i class="fa-solid fa-eye"></i> Xem trước
                  </span>
                </a>
              </div>
              <div class="clearfix"></div>
            </div>
            <div class="template-cv-item_info">
              <div class="tag-list">
                Chuyên nghiệp
                Đơn giản
                <a href="javascript:void(0)" class="template-cv-item-tag">+8</a>
              </div>
              <div class="template-cv-title">
                <h2>Hiện đại</h2>
              </div>
            </div>
          </div>
          </div>

          <div class="col-md-3 col-sm-4 list-cv-style_item">
        <div class="template-cv-item box-shadow">
            <div class="cv-img">
              <div class="cv-img-tag">
                <div class="cv-img-tag_item tag-ver2">
                  <i class="fa-solid fa-bolt-lightning"></i> Powered by CV Builder 2.0
                </div>
              </div>
              <img src="https://www.topcv.vn/images/cv/screenshots/thumbs/cv-template-thumbnails-v1.2/basic_4_v2.png?v=1.0.6" alt="Mẫu CV tiếng Việt" title="Mẫu CV tiếng Việt" width="450" height="500" class="img-responsive lazy">
              <div class="cv-overlay">
                <a class="chooseCvData btn-use-now">
                  <span class="create-cv-button">
                    <router-link to="cv" class="">Dùng mẫu</router-link>
                  </span>
                </a>
                <a @click="showDialog" href="javascript:void(0)" class="btn-preview preview-cv-template-button">
                  <span class="preview-button">
                    <i class="fa-solid fa-eye"></i> Xem trước
                  </span>
                </a>
              </div>
              <div class="clearfix"></div>
            </div>
            <div class="template-cv-item_info">
              <div class="tag-list">
                Chuyên nghiệp
                Đơn giản
                <a href="javascript:void(0)" class="template-cv-item-tag">+8</a>
              </div>
              <div class="template-cv-title">
                <h2>Mẫu 2</h2>
              </div>
            </div>
          </div>
          </div>

          <div class="col-md-3 col-sm-4 list-cv-style_item">
        <div class="template-cv-item box-shadow">
            <div class="cv-img">
              <div class="cv-img-tag">
                <div class="cv-img-tag_item tag-ver2">
                  <i class="fa-solid fa-bolt-lightning"></i> Powered by CV Builder 2.0
                </div>
              </div>
              <img src="https://www.topcv.vn/images/cv/screenshots/thumbs/cv-template-thumbnails-v1.2/basic_5_v2.png?v=1.0.6" alt="Mẫu CV tiếng Việt" title="Mẫu CV tiếng Việt" width="450" height="500" class="img-responsive lazy">
              <div class="cv-overlay">
                <a :href="'/cv/' + formId" class="chooseCvData btn-use-now">
                    <span class="create-cv-button">
                      Dùng mẫu
                    </span>
                </a>
                <a @click="showDialog" href="javascript:void(0)" class="btn-preview preview-cv-template-button">
                  <span class="preview-button">
                    <i class="fa-solid fa-eye"></i> Xem trước
                  </span>
                </a>
              </div>
              <div class="clearfix"></div>
            </div>
            <div class="template-cv-item_info">
              <div class="tag-list">
                Chuyên nghiệp
                Đơn giản
                <a href="javascript:void(0)" class="template-cv-item-tag">+8</a>
              </div>
              <div class="template-cv-title">
                <h2>Tối giản</h2>
              </div>
            </div>
          </div>
          </div>

          

          
      </div>
    </div>
  </div>


          

          <!-- mẫu cv ứng tuyển -->
          
          <div class="box-slide">
            <div class="box-slide-header">
              <h2 class="title">Mẫu CV ứng tuyển các vị trí phổ biến</h2>
              <div class="action">
                <div class="btn-location left slick-arrow" id="btn-pre-list-category" style="display: flex;">
                  <i class="fa-solid fa-chevron-left"></i>
                  </div>
                  <div class="btn-location left slick-arrow" id="btn-pre-list-category" style="display: flex;">
                    <i class="fa-solid fa-chevron-right"></i>
                    </div>
              </div>
            </div>
          </div>
          <div class="box-slide-item">
            <div class="slider-item">
              <div class="item-image">
                <img src="../assets/image/case.png" alt="" />
              </div>
              <div class="item-title">Nhân viên lễ tân hành chính</div>
                  <router-link to="/login" class="icon">
                    <i class="fa-solid fa-user"></i>
                  </router-link>
            </div>
            <div class="slider-item">
              <div class="item-image">
                <img src="../assets/image/case.png" alt="" />
              </div>
              <div class="item-title">Nhân viên lễ tân hành chính</div>
            </div>
            <div class="slider-item">
              <div class="item-image">
                <img src="../assets/image/conversation.png" alt="" />
              </div>
              <div class="item-title">Nhân viên bán hàng</div>
            </div>
            <div class="slider-item">
              <div class="item-image">
                <img src="../assets/image/marketing.webp" alt="" />
              </div>
              <div class="item-title">Chuyên viên marketing</div>
            </div>
            <div class="slider-item">
              <div class="item-image">
                <img src="../assets/image/money_ticket.webp" alt="" />
              </div>
              <div class="item-title">Giám đốc quan hệ khách hàng</div>
            </div>
            <div class="slider-item">
              <div class="item-image">
                <img src="../assets/image/case.png" alt="" />
              </div>
              <div class="item-title">Nhân viên lễ tân hành chính</div>
            </div>
          </div>
          <div class="img-desktop">
            <img src="../assets/image/banner_new.png" alt="" />
          </div>

  <!-- bài viết được đề xuất -->
          <div class="box-slide">
            <div class="box-slide-header">
              <h2 class="title">Bài viết được đề xuất</h2>
              <div class="action">
                <div class="btn-location left slick-arrow" id="btn-pre-list-category" style="display: flex;">
                  <i class="fa-solid fa-chevron-left"></i>
                  </div>
                  <div class="btn-location left slick-arrow" id="btn-pre-list-category" style="display: flex;">
                    <i class="fa-solid fa-chevron-right"></i>
                    </div>
              </div>
            </div>
          </div>
          <div class="box-slide-item">
            <div class="article-item">
              <div class="article-image">
                <img
                  src="../assets/image/cach-viet-cv-cho-sinh-vien-chua-tot-nghiep-topcv.jpg63f32239a08d3 (1).jpg"
                  alt=""
                />
              </div>
              <div class="item-title">
                CV cho sinh viên chưa tốt nghiệp nên viết như nào
              </div>
            </div>
            <div class="article-item">
              <div class="article-image">
                <img
                  src="../assets/image/related_post_default.webp"
                  alt=""
                />
              </div>
              <div class="item-title">
                CV SV THPT
              </div>
            </div>
            <div class="article-item">
              <div class="article-image">
                <img
                  src="../assets/image/cv-la-gi.png"
                  alt=""
                />
              </div>
              <div class="item-title">
                CV là gì? Những lưu ý khi viết CV xin việc
              </div>
            </div>
            <div class="article-item">
              <div class="article-image">
                <img
                  src="../assets/image/cv-tieng-han-thumb-fb.webp"
                  alt=""
                />
              </div>
              <div class="item-title">
                Hướng dẫn viết CV xin việc bằng tiếng hàn chuẩn 2024
              </div>
            </div>
          </div>     
        </div>
      </main>
      <footer id="footer-desktop">
        <div class="footer-common-search-keywords">
        </div>
        <div class="footer-main">
          <div class="container">
            <div class="box-main">
              <div class="column">
                  <img
                    src="../assets/image/logoheader.webp"
                    id="img-logo-footer"
                  />
                <div class="box-contact">
                  <p class="title">Liên hệ</p>
                  <span>Hotline:</span
                  ><a href="tel:02466805588">(024) 6680 5588 (Giờ hành chính)</a
                  ><br />
                  <span>Email:</span
                  ><a href="mailto:hotro@topcv.vn">huykit@gmail.com</a>
                </div>
                <div class="box-download">
                  <p class="title">Ứng dụng tải xuống</p>
                  <div class="btn-download-app">
                    <a
                      target="_blank"
                      ><img
                        class="img-responsive"
                        src="https://cdn-new.topcv.vn/unsafe/https://static.topcv.vn/v4/image/welcome/download/app_store.png"
                        alt="Tai app TopCV tai App Store"
                        title="Tải app TopCV tại App Store"
                    /></a>
                    <a
                      target="_blank"
                      ><img
                        class="img-responsive"
                        src="https://cdn-new.topcv.vn/unsafe/https://static.topcv.vn/v4/image/welcome/download/chplay.png"
                        alt="Tai app TopCV tai Google Play"
                        title="Tải app TopCV tại Google Play"
                    /></a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </footer>

      <!-- /form đăng kí -->
    <div>
      <button @click="showRegisterModal = true">Đăng ký</button>
      <div v-if="showRegisterModal" class="modal">
        <div class="modal-content">
          <span class="close" @click="showRegisterModal = false">&times;</span>
          <h2 class="font" > Đăng Ký</h2>
          <form @submit.prevent="register">
            <div class="signup">
              <label for="fullname">Tên đầy đủ:</label>
              <input type="text" id="fullname" v-model="fullname" @focus="clearError('fullname')" />
              <span class="error" v-if="fullnameError">{{ fullnameError }}</span>
            </div>
            <div class="signup">
              <label for="email">Email:</label>
              <input type="email" id="email" v-model="email" @focus="clearError('email')" />
              <span class="error" v-if="emailError">{{ emailError }}</span>
            </div>
            <div class="signup">
              <label for="password">Mật khẩu:</label>
              <input type="password" id="password" v-model="password" @focus="clearError('password')" />
              <span class="error" v-if="passwordError">{{ passwordError }}</span>
            </div>
            <div class="signup">
              <label for="passwordConfirmation">Xác nhận mật khẩu:</label>
              <input type="password" id="passwordConfirmation" v-model="passwordConfirmation" @focus="clearError('passwordConfirmation')" />
              <span class="error" v-if="passwordConfirmationError">{{ passwordConfirmationError }}</span>
            </div>
            <button class="form-submit" type="submit">Đăng ký</button>
          </form>
        </div>
      </div>
    </div>

    <!-- form đăng nhập -->
    <div class="modal_login" v-if="showLoginModal && !isLoggedIn" @click="closeModalOnClickOutside">
    <div class="modal_main_login" @click.stop>
      <form @submit.prevent="login" class="form" id="login-form">
        <div class="modal_close_login" @click="showLoginModal = false"><i class="fa-solid fa-x"></i></div>
        <h3 class="heading">Đăng Nhập</h3>
        <div class="spacer"></div>
        <div class="form-group">
          <label for="username" class="form-label">Tên Đăng Nhập</label>
          <input v-model="loginUsername" @focus="clearError('loginUsername')" id="username" type="text" placeholder="VD: abc@gmail.com" class="form-control">
          <span class="form-message" v-if="loginUsernameError">{{ loginUsernameError }}</span>
        </div>
        <div class="form-group">
          <label for="password_login" class="form-label">Mật khẩu</label>
          <input v-model="loginPassword" @focus="clearError('loginPassword')" id="password_login" type="password" placeholder="Nhập mật khẩu" class="form-control">
          <span class="form-message" v-if="loginPasswordError">{{ loginPasswordError }}</span>
        </div>
        <button type="submit" class="form-submit">Đăng Nhập</button>
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';
import { collection, addDoc, getDocs, query, where } from 'firebase/firestore';
import db from '@/firebase';
import DetailCV from '../components/DetailCV.vue';

const showRegisterModal = ref(false);
const fullname = ref('');
const email = ref('');
const password = ref('');
const passwordConfirmation = ref('');
const isLoggedIn = ref(false);
const fullnameError = ref('');
const emailError = ref('');
const passwordError = ref('');
const passwordConfirmationError = ref('');
const users = ref([]);
const showModal = ref(false);
const showLoginModal = ref(false);
const loginUsername = ref('');
const loginPassword = ref('');
const loginUsernameError = ref('');
const loginPasswordError = ref('');

const clearError = (field) => {
  if (field === 'loginUsername') loginUsernameError.value = '';
  if (field === 'loginPassword') loginPasswordError.value = '';
  if (field === 'fullname') fullnameError.value = '';
  if (field === 'email') emailError.value = '';
  if (field === 'password') passwordError.value = '';
  if (field === 'passwordConfirmation') passwordConfirmationError.value = '';
};

const validateRegisterForm = () => {
  fullnameError.value = '';
  emailError.value = '';
  passwordError.value = '';
  passwordConfirmationError.value = '';

  if (!fullname.value.trim()) {
    fullnameError.value = 'Vui lòng nhập tên đầy đủ';
  }
  const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  if (!email.value.trim()) {
    emailError.value = 'Vui lòng nhập email';
  } else if (!emailPattern.test(email.value)) {
    emailError.value = 'Email không hợp lệ';
  }
  if (!password.value.trim()) {
    passwordError.value = 'Vui lòng nhập mật khẩu';
  } else if (password.value.length < 6) {
    passwordError.value = 'Mật khẩu phải chứa ít nhất 6 kí tự';
  }
  if (passwordConfirmation.value !== password.value) {
    passwordConfirmationError.value = 'Mật khẩu nhập lại không khớp';
  }
};

const register = async () => {
  validateRegisterForm();
  if (!fullnameError.value && !emailError.value && !passwordError.value && !passwordConfirmationError.value) {
    try {
      // Lưu thông tin đăng ký vào Firestore
      await addDoc(collection(db, 'users'), {
        fullname: fullname.value,
        email: email.value,
        password: password.value
      });

      showToastMessage('Đăng ký thành công!');
      // Cập nhật thông tin đăng nhập cho form đăng nhập
      showRegisterModal.value = false;
      isLoggedIn.value = true;
    } catch (e) {
      console.error("Error adding document: ", e);
      showToastMessage('Đăng ký thất bại, vui lòng thử lại.');
    }
  }
};

const showToastMessage = (message) => {
  alert(message);
};

onMounted(async () => {
  await getUsers();
});
const router = useRouter();

const logout = () => {
  isLoggedIn.value = false;
  router.push('/');
};

const getUsers = async () => {
  try {
    const querySnapshot = await getDocs(collection(db, 'users'));
    users.value = querySnapshot.docs.map(doc => doc.data());
  } catch (error) {
    console.error('Error getting users: ', error);
  }
};

const login = async () => {
  try {
    // Truy vấn người dùng với email tương ứng từ Firestore
    const q = query(collection(db, 'users'), where('email', '==', loginUsername.value));
    const querySnapshot = await getDocs(q);

    // Kiểm tra xem có tài liệu người dùng được trả về không
    if (querySnapshot.docs.length === 0) {
      showToastMessage('Người dùng không tồn tại.');
      return;
    }

    // Kiểm tra mật khẩu
    const userDoc = querySnapshot.docs[0].data();
    if (userDoc.password !== loginPassword.value) {
      showToastMessage('Mật khẩu không đúng.');
      return;
    }

    isLoggedIn.value = true;
    showLoginModal.value = false;
  } catch (error) {
    console.error('Error logging in: ', error);
    showToastMessage('Đã xảy ra lỗi. Vui lòng thử lại sau.');
  }
};


  const closeModalOnClickOutside = (event) => {
    if (!event.target.closest('.form') && !event.target.closest('.register-info')) {
      showModal.value = false;
      showLoginModal.value = false;
      showRegisterModal.value = false;
    }
  };



  </script>
  <script>
  export default {
    data() {
      return {
        formId: 1 
      };
    }
  };
  </script>

  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  @import url(/src/assets/css/style.css);
  @import url(/src/assets/css/cmt.css);
  </style>