<template>
    <div class="profile-container">
        <div class="profile-main">
            <div class="profile-header">
                <div class="profile-header-img">
                    <img src="@/static/img/profile-ava.jpg" alt="">
                </div>
                <div class="profile-header-info">
                    <div class="profile-header-info-name"><p>duyenn01</p></div>
                    <div class="profile-header-info-btnEdit"><el-button>Chỉnh sửa trang cá nhân</el-button></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Profile',
    data() {

    }
}
</script>

<style lang="scss">
.profile-container {
    margin: 0px;
    padding: 0px;
    .profile-main {
        padding: 30px 20px;
        width: calc(100% - 150px);
        margin: auto;
        .profile-header {
            margin-bottom: 44px;
            .profile-header-img {
                margin-right: 30px;
                max-width: 350px;
                img {
                    height: 150px;
                    width: 150px;
                    margin-right: auto;
                    margin-left: auto;
                }
            }
        }
    }
}
</style>