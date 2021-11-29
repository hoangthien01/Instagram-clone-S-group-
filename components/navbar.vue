<template>
<div class="navbar-wrapper">
  <div class="navbar">
    <div class="navbar-logo">
      <div>
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
        <img v-show="navActive !== 'home'" @click="changeActiveNav('home')" src="@/static/img/homeWhite.png" alt="" srcset="">
        <img v-show="navActive === 'home'" src="@/static/img/home.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'direct'" @click="changeActiveNav('direct')" src="@/static/img/directWhite.png" alt="" srcset="">
        <img v-show="navActive === 'direct'" src="@/static/img/direct.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'add'" @click="changeActiveNav('add')" src="@/static/img/addWhite.png" alt="" srcset="">
        <img v-show="navActive === 'add'" src="@/static/img/add.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'compass'" @click="changeActiveNav('compass')" src="@/static/img/compassWhite.png" alt="" srcset="">
        <img v-show="navActive === 'compass'" src="@/static/img/compass.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
        <img v-show="navActive !== 'heart'" @click="changeActiveNav('heart')" src="@/static/img/heartWhite.png" alt="" srcset="">
        <img v-show="navActive === 'heart'" src="@/static/img/heart.png" alt="" srcset="">
      </div>
      <div class="navbar-actions__item">
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
    }
  }

}
</script>

<style lang="scss" scoped>
.navbar-wrapper {
  height: 56px;
  padding: 13px 20px;
  border-bottom: 1px solid #d6d3d3;

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

    }
  }
}
</style>