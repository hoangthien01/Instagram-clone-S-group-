<template>
  <div class="login-wrapper">
    <div class="login-content">
      <div class="login-content__info">
        <div class="login-content__head">
          <div class="login-content__title"></div>
          <div class="login-content__subtitle">
            Sign up to see photos and videos from your friends.
          </div>
          <el-button type="primary" class="login-content__facebook">
            <span class="login-content__facebook-image"></span>
            Đăng nhập bằng facebook
          </el-button>
          <div class="line">
            HOẶC
          </div>
          <div class="login-content__form">
            <el-form ref="login-form" :model="form" :rules="rules">
              <el-form-item prop="phone">
                <el-input v-model="form.phone" placeholder="Số điện thoại hoặc email"></el-input>
              </el-form-item>
              <el-form-item prop="fullName">
                <el-input v-model="form.fullName" placeholder="Tên đầy đủ"></el-input>
              </el-form-item>
              <el-form-item prop="userName">
                <el-input v-model="form.userName" placeholder="Tên người dùng"></el-input>
              </el-form-item>
              <el-form-item prop="passWord">
                <el-input v-model="form.passWord" placeholder="Mật khẩu"></el-input>
              </el-form-item>
               <el-form-item>
                <el-button type="primary" class="btn-login" @click="onSubmit" >Login</el-button>
              </el-form-item>
            </el-form>
            <div class="login-content__forgot_password">
              By signing up, you agree to our Terms , Data Policy and Cookies Policy .
            </div>
          </div>
        </div>
        <div class="login-content__middle">
          <p>Bạn đã có tài khoản? <span @click="navigateLogin">Đăng nhập</span></p>
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
  </div>
</template>

<script>
export default {
  name: 'Register',
  layout: 'unauth',
  data() {
    return {
      form: {
        phone: '',
        fullName: '',
        userName: '',
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
  methods: {
    navigateLogin() {
      this.$router.push('/auth/login')
    }
  }
}
</script>

<style lang="scss" scoped>
.login-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  flex-direction: column;
  
  .login-content {
    display: flex;
    align-items: flex-start;
    padding: 15px 0 10px;

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
          margin: 15px auto;
          background-image: url('~static/img/main.png');
          background-repeat: no-repeat;
          background-position: 0 -130px;
          height: 51px;
          width: 175px;
        }

        .login-content__subtitle {
          color: rgba(var(--f52,142,142,142),1);
          font-size: 17px;
          font-weight: 600;
          line-height: 20px;
          text-align: center;
        }

        .login-content__facebook {
          margin:20px 0 0 ;
          font-size: 14px;
          color: #385185;
          font-weight: 600;
          cursor: pointer;
          width: 100%;
          height: 32px;
          padding: 0;

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

        .line  {
          margin: 10px 0 18px;
          text-align: center;
          font-size: 13px;

        }

        .login-content__form {
          text-align: center;

          .el-form-item {
            margin-bottom: 5px;

            .el-input {
              font-size: 13px;
            }
          }

          .login-content__forgot_password {
           color: rgba(var(--f52,142,142,142),1);
            font-size: 12px;
            line-height: 16px;
            margin: 10px 0;
            text-align: center;
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
}
</style>