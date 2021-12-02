<template>
  <div class="post">
    <div  class="post-header">
      <div class="post-header__left">
        <div class="post-header__avatar">
          <div class="avatar-wrapper">
            <img src="https://scontent.fdad3-1.fna.fbcdn.net/v/t39.30808-6/263321377_10160075726328598_3966164101833339520_n.jpg?_nc_cat=1&ccb=1-5&_nc_sid=730e14&_nc_ohc=3nNh9QQXKiIAX-dw9FQ&_nc_ht=scontent.fdad3-1.fna&oh=d0d0e0f69bdbfde11fe866919a942ff3&oe=61ADE94A" alt="">
          </div>
        </div>
        <div>
          <div class="post-header__name">hoangthien01</div>
          <div class="post-header__description">nou camp</div>
        </div>
      </div>
      <div class="post-header__more">
        <i class="el-icon-more"></i>
      </div>
    </div>
    <div class="post-content">
      <div class="post-content__image">
        <img src="https://scontent.fdad3-1.fna.fbcdn.net/v/t39.30808-6/261322335_5420531627961826_1054343762841441122_n.png?_nc_cat=1&ccb=1-5&_nc_sid=730e14&_nc_ohc=_9cRz9ipx28AX-Oi64w&_nc_ht=scontent.fdad3-1.fna&oh=41bdd3672403146eb9ca8249e8ac3d98&oe=61ACD0C5" alt="" srcset="">
      </div>
      <div class="post-content__info">
        <div class="post-content__info-actions">
          <div class="left">
            <fa class="action-item" :icon="['far','heart']"/>
            <fa class="action-item" :icon="['far','comment']"/>
            <fa class="action-item" :icon="['far','paper-plane']"/>
          </div>
          <div class="right">
            <fa class="action-item" :icon="['far','bookmark']"/>
          </div>
        </div>
        <div class="post-content__info-main">
          <div class="post-content__info-numver__likes">376 likes</div>
          <div class="post-content__info-text">fcbarcelona We got fun and games
          🎾 Divertida sessió al gimnàs
          😂 Diversión y juegos en el gimnasio
          </div>
          <div class="post-content__info-more__comments">View all 2,722 comments</div>
          <div class="post-content__info-time">1 DAY AGO</div>
        </div>
      </div>
    </div>
    <div  class="post-footer">
      <fa class="post-smile-icon" :icon="['far','smile']" @click="openEmoijPicker"/>
      <VEmojiPicker v-show="isShowIcon" class="emoij-wrapper" :pack="pack" @select="selectEmoji" />
      <el-input v-model="comment" class="post-comment__input" placeholder="Add a comment..."/>
      <div class="btn-post" :class="{'opacity': comment === ''}">
        <span>Post</span>
      </div>
    </div>
</div>
</template>

<script>

import { VEmojiPicker, categoriesDefault } from "v-emoji-picker";
export default {
  name: 'Post',
  components: {
    VEmojiPicker
  },
  data() {
    return {
      comment: '',
      pack: categoriesDefault,
      isShowIcon: false
    }
  },
  methods : {
    openEmoijPicker() {
      this.isShowIcon = !this.isShowIcon
    },
    selectEmoji(emoji) {
      console.log(emoji)
      this.isShowIcon = false
    }
  }
}
</script>

<style lang="scss" scoped>

.opacity {
  opacity: 0.3;
}
.post {
  background-color: #fff;
  margin-bottom: 24px;

  .post-header {
    padding: 14px 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid rgba(var(--ce3,239,239,239),1);

    .post-header__left {
      display: flex;
      align-items: center;

      .post-header__name {
        font-size: 14px;
        cursor: pointer;
      }

      .post-header__description {
        font-size: 12px;
        cursor: pointer;
      }

      .post-header__avatar {
        border-radius: 50%;
        margin-right: 15px;
        cursor: pointer;
        width: 40px;
        height: 40px;
        border: 3px solid #C83593;
        overflow: hidden;
        display: flex;
        align-items: center;
        justify-content: center;

        .avatar-wrapper {
          border-radius: 50%;
          width: 32px;
          height: 32px;
          border: 1px solid #ccc;
          overflow: hidden;

          img {
            width: 100%;
            object-fit: cover;

          }
        }
      }
    }

    .post-header__more {
      cursor: pointer;
    }
  }

  .post-content {
    overflow: hidden;

    .post-content__image {


      img {
        object-fit: cover;
        width: 100%;
      }
    }

    .post-content__info {
      margin-top: 4px;

      .post-content__info-actions {

        padding: 6px 16px 8px;
        display: flex;
        align-items: center;
        justify-content: space-between;

        .action-item {
          font-size: 24px;
          margin: 0 10px;
          cursor: pointer;
        }

        .action-item:first-child {
          margin: 0;
        }
        .action-item:last-child {
          margin: 0;
        }
      }

      .post-content__info-main {
        padding: 0 16px;

        .post-content__info-numver__likes {
          margin-bottom: 8px;
          font-size: 14px;
          font-weight: 600;
        }

        .post-content__info-text {
          font-size: 14px;
          word-break: break-word;
          white-space: pre-wrap;
        }

        .post-content__info-more__comments {
          font-size: 14px;
          color: #8e8e8e;
          margin: 5px 0 10px;
        }

        .post-content__info-time {
          font-size: 10px;
          color: #8e8e8e;
          margin-bottom: 16px;
        }
      }
    }
  }

  .post-footer {
    border-top: 1px solid rgba(var(--ce3,239,239,239),1);
    display: flex;
    align-items: center;
    padding: 6px 16px;
    position: relative;

    .post-smile-icon {
      font-size: 24px;
      box-sizing: content-box;
      padding: 8px 16px 8px 0;
      cursor: pointer;
    }

    ::v-deep.el-input__inner {
      border: none;
      color: #000;
    }

    .btn-post {
      color: #0095f6;
      font-size: 14px;
      cursor: pointer;
      padding: 8px 0 8px 16px;
    }

    .emoij-wrapper {
      position: absolute;
      bottom: 50px;
      z-index: 9999;
    }

  }
}
</style>