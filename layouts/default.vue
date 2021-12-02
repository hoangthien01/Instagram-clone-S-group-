<template>
  <div>
    <navbar></navbar>
    <div class="content">
      <Nuxt/>
    </div>
  </div>
</template>

<script>
import Navbar from '~/components/navbar.vue'
export default {
  name:'Default',
  components: {
    Navbar
  }
}
</script>

<style lang="scss" scoped>
.content {
  min-height:calc(100vh - 56px);
  background-color: #fafafa;
}
</style>