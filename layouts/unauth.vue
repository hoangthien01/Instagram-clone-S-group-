<template>
  <div class="unauth-layout">
    <Nuxt/>
  </div>
</template>

<script>
export default {
}
</script>

<style>
body {
  margin: 0;
  box-sizing: border-box;
}
</style>
<style lang="scss" scoped>
* {
  margin: 0;
  box-sizing: border-box;
}

.unauth-layout {
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  background-color: #FAFAFA;
}
</style>