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
        <fa icon="home"/>
      </div>
      <div class="navbar-actions__item">
        <fa :icon="['far', 'comment-dots']"/>
      </div>
      <div class="navbar-actions__item">
        <fa :icon="['far', 'plus-square']"/>
      </div>
      <div class="navbar-actions__item">
        <fa :icon="['far', 'compass']"/>
      </div>
      <div class="navbar-actions__item">
        <fa :icon="['far', 'heart']"/>
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
      searchInp: ''
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

        .svg-inline--fa {
          font-size: 23px;
          color: #181717;
        }
      }

    }
  }
}
</style>