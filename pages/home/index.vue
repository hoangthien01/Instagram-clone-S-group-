<template>
  <div class="home-container">
    <div class="home-main">
      <Story/>
      <Post/>
    </div>
  </div>
</template>

<script>
import Story from '@/components/story'
import Post from '@/components/post'
export default {
  name:'Home',
  components : {
    Story,Post
  },
  layout: 'default'
}
</script>

<style lang="scss" scoped>
.home-container {
  width: 100%;
  max-width: 945px;
  margin: auto;
  display: flex;
  min-height: calc(100vh - 56px);
  padding-top: 30px;

  .home-main {
    width: 100%;
    max-width: 618px;
  }
}


</style>