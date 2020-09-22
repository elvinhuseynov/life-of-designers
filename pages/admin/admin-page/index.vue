<template>
  <div class="main container">
    <div class="home-update">
      <nuxt-link to="/admin/admin-page/home-page-updates">Home Page Updates</nuxt-link>
    </div>
    <div class="home-update">
      <nuxt-link to="/admin/admin-page/about-page-updates">About Page Updates</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.main {
  display: flex;
  width: 100%;
  justify-content: space-around;

  a {
    color: black;
  }

  a:hover{
    border-bottom: 0;
  }
}
</style>