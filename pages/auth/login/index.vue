<template>
  <div class="login-wrapper">
    <div class="login-content">
      <div class="login-content__bg">
        <img src="@/static/img/bg-login.png" alt="" srcset="" />
          <div class="slider">
            <transition name="fade" mode="out-in">
              <img v-if="imageID == 1" class="slider-image" src="@/static/img/bg-login1.jpg" alt="" srcset=""/>
              <img v-if="imageID == 2" class="slider-image" src="@/static/img/bg-login2.jpg" alt="" srcset=""/>
              <img v-if="imageID == 3" class="slider-image" src="@/static/img/bg-login3.jpg" alt="" srcset=""/>
              <img v-if="imageID == 4" class="slider-image" src="@/static/img/bg-login4.jpg" alt="" srcset=""/>
              <img v-if="imageID == 5" class="slider-image" src="@/static/img/bg-login5.jpg" alt="" srcset=""/>
            </transition>
          </div>
      </div>
      <div class="login-content__info">
        <div class="login-content__head">
          <div class="login-content__title"></div>
          <div class="login-content__form">
            <el-form ref="login-form" :model="form" :rules="rules">
              <el-form-item prop="name">
                <el-input v-model="form.name" placeholder="Số điện thoại, tên người dùng hoặc email"></el-input>
              </el-form-item>
              <el-form-item prop="passWord">
                <el-input v-model="form.passWord" placeholder="Mật khẩu"></el-input>
              </el-form-item>
               <el-form-item>
                <el-button type="primary" class="btn-login" @click="onSubmit" >Login</el-button>
              </el-form-item>
            </el-form>

            <div class="line">
              HOẶC
            </div>
            <div class="login-content__facebook">
              <span class="login-content__facebook-image"></span>
              Đăng nhập bằng facebook
            </div>
            <div class="login-content__forgot_password">
              Quên mật khẩu
            </div>
          </div>
        </div>
        <div class="login-content__middle">
          <p>Bạn chưa có tài khoản ư? <span @click="navigateRegister">Đăng kí</span></p>
        </div>
        <div class="login-content__bottom">
          <p>Tải ứng dụng</p>
          <div class="download">
            <img class="download-img" src="@/static/img/app-store.png" alt="" srcset="">
            <img class="download-img"  src="@/static/img/google-play.png" alt="" srcset="">
          </div>
        </div>
      </div>
    </div>
    <footer class="footer">
      <div class="footer-item">
        <span>Meta</span> 
        <span>About</span>
        <span>Blog</span>
        <span>Jobs</span>
        <span>Help</span>
        <span>API</span>
        <span>Privacy</span>  
        <span>Terms</span>  
        <span>Top</span> 
        <span>Accounts</span> 
        <span>Hashtags</span> 
        <span>Locations</span> 
        <span>Instagram</span>   
        <span>Lite</span>    
      </div>
      <div class="footer-item">
        <span>Beauty</span>
        <span>Dance</span>  
        <span>Fitness</span>  
        <span>Food & Drink</span> 
        <span>Home & Garden</span> 
        <span>Music</span> 
        <span>Visual Arts</span> 
      </div>
      <div class="footer-item">
        <span>English</span>
        <span>English© 2021 Instagram from Meta</span>       
      </div>

    </footer>
  </div>
</template>

<script>
export default {
  name: 'Login',
  layout: 'unauth',
  data() {
    return {
      form: {
        name: '',
        passWord: '',
      },
      rules: {
        name: [
          { required: true, message: 'Please input your name', trigger:  ['change'] },
        ],
        passWord: [
          { required: true, message: 'Please input your password', trigger: ['change','blur'] }
        ],
      },
      imageID : 1
    }
  },
  mounted() {
    setInterval(() => {
      if (this.imageID === 5) { this.imageID = 1 }
      else {
        this.imageID++
      }
    },3500)
  },
   methods: {
    navigateRegister() {
      this.$router.push('/auth/register')
    }
  }
}
</script>

<style lang="scss" scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 1s ease;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.login-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  flex-direction: column;

  .login-content__bg {
    position: relative;

    .slider {
      position: absolute;
      top: 95px;
      left: 147px;
      width: 247px;
      height: 436px;
      object-fit: cover;

      .slider-image {
        width: 100%;
        height: 100%;
      }
    }
  }
  
  .login-content {
    display: flex;
    align-items: flex-start;
    padding: 30px 0 10px;

    &__info {
      height: 100%;
      width: 350px;

      .login-content__head {
        background-color: #fff;
        padding: 10px 35px 24px;
        border: 1px solid #ccc;
        margin-top: 30px;
        min-width: 348px;
        box-sizing: border-box;

        .login-content__title {
          font-size: 30px;
          text-align: center;
          margin: 22px auto;
          background-image: url('~static/img/main.png');
          background-repeat: no-repeat;
          background-position: 0 -130px;
          height: 51px;
          width: 175px;
        }

        .login-content__form {
          text-align: center;

          .el-form-item {
            margin-bottom: 20px;

            .el-input {
              font-size: 13px;
            }
          }

          .line {
            font-size: 13px;
          }

          .login-content__facebook {
            margin:20px 0 0 ;
            font-size: 14px;
            color: #385185;
            font-weight: 600;
            cursor: pointer;

            &-image {
              background-image: url('~static/img/main.png');
              background-repeat: no-repeat;
              background-position: -414px -259px;
              height: 16px;
              width: 16px;
              display: inline-block;
              margin-right: 8px;
              position: relative;
              top: 3px;
            }
          }

          .login-content__forgot_password {
            margin-top: 10px;
            font-size: 12px;
            cursor: pointer;
            color: #00376b;
          }

          .btn-login {
            width: 100%;
          }
        }
      }

      .login-content__middle {
        margin-top: 20px;
        border: 1px solid #ccc;
        background-color: #fff;
        padding: 20px 0;
        text-align: center;
        font-size: 14px;
        
        span {
          color: #0095f6;
          cursor: pointer;
        }
      }

      .login-content__bottom {
        text-align: center;
        margin-top: 10px;
        font-size: 13px;

        .download {
          margin-top: 10px;
          .download-img {
            width: 132px;
            cursor: pointer;
          }
        }
      }
    }
  }

  .footer {
    text-align: center;
    color: #8e8e8e;

    &-item {
      margin-top: 5px;
      font-size: 12px;

      span {
        margin: 0 5px;
      }
    }
  }
}
</style>