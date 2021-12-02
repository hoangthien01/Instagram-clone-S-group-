<template>
<div class="navbar-wrapper">
  <div class="navbar">
    <div class="navbar-logo">
      <div @click="navigateHome">
        <img src="@/static/img/logo.png" alt="" srcset="">
      </div>
    </div>
    <div class="navbar-search">
      <el-input
        v-model="searchInp"
        placeholder="Search"
        clearable
      >
        <i slot="prefix" class="el-input__icon el-icon-search"></i>
      </el-input>
    </div>

    <div class="navbar-actions">
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'home'" src="@/static/img/homeWhite.png" alt="" srcset="" @click="changeActiveNav('home')">
        <img v-show="navActive === 'home'" src="@/static/img/home.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'direct'" src="@/static/img/directWhite.png" alt="" srcset="" @click="changeActiveNav('direct')">
        <img v-show="navActive === 'direct'" src="@/static/img/direct.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'add'" src="@/static/img/addWhite.png" alt="" srcset="" @click="changeActiveNav('add')">
        <img v-show="navActive === 'add'" src="@/static/img/add.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'compass'" src="@/static/img/compassWhite.png" alt="" srcset="" @click="changeActiveNav('compass')">
        <img v-show="navActive === 'compass'" src="@/static/img/compass.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'heart'" src="@/static/img/heartWhite.png" alt="" srcset="" @click="changeActiveNav('heart')">
        <img v-show="navActive === 'heart'" src="@/static/img/heart.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item avatar">
        <el-avatar  size="small" ></el-avatar>
      </div>

    </div>

  </div>
</div>
</template>

<script>
export default {
  name:'Navbar',
  data() {
    return {
      searchInp: '',
      navActive: 'home'
    }
  },
  methods : {
    changeActiveNav(data) {
      this.navActive = data
    },
    
    navigateHome() {
      this.$router.push('/')
    }
  }

}
</script>

<style lang="scss" scoped>
.navbar-wrapper {
  height: 56px;
  padding: 13px 20px;
  border-bottom: 1px solid rgba(var(--b6a,219,219,219),1);

  .navbar {
    margin: auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 940px;

    .navbar-logo {
      width: 38.4%;

      div {
        cursor: pointer;

        img {
          display: block;
        }
      }
    }

    .navbar-search {
    
        ::v-deep.el-input__inner {
          height: 28px;
          width: 215px;
          background-color: #fafafa;
        }

        ::v-deep.el-input__icon {
          line-height: unset;
        }
    }

    .navbar-actions {
      width: 38.4%;
      display: flex;
      align-items: center;
      justify-content: flex-end;
      padding-left: 24px;

      &__item {
        margin-left: 22px;
        cursor: pointer;

        img {
          width: 23px;
        }
      }

      .avatar {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
      }

      .avatar::before {
        content: '';
        display: block;
        position: absolute;
        width: calc(100% + 4px);
        height: calc(100% + 4px);
        border: 1px solid #ccc;
        left: -2px;
        top: -2px;
        border-radius: 50%;
      }

    }
  }
}
</style>