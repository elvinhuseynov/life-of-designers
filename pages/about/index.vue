<template>
  <div class="container images">
    <nuxt-link to="/about/murad_karimli" class="image">
      <img id="img" src="../../assets/Murad2.jpg" alt />
      <div id="img-info" class="img-info">
        <span>Murad Karimli</span>
        <span>Architect</span>
      </div>
    </nuxt-link>
    <nuxt-link to="/about/rahman_aliyev" class="image img-2">
      <img id="img" src="../../assets/rahman2.jpg" alt />
      <div id="img-info" class="img-info">
        <span>Rahman Aliyev</span>
        <span>Graphic Designer/3D Modeller</span>
      </div>
    </nuxt-link>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
a {
  color: black;
  text-decoration: none;
  border: none;
}

.images {
  width: 100%;
  display: flex;
  justify-content: space-between;

  .image {
    width: 45%;
    position: relative;

    img {
      width: 100%;
      max-height: 80vh;
    }

    .img-info {
      display: none;
      position: absolute;
      flex-direction: column;
      font-weight: bold;
      align-items: center;
      width: 100%;
      top: 70%;
      left: 0%;
    }
  }
}

.img-2 {
  margin-right: 15px;
}

.image:hover {
  img {
    opacity: 0.3;
  }
}

#img:hover + #img-info {
  display: flex;
}

@media screen and (max-width: 992px) {
  .images {
    display: flex;
    flex-direction: column;

    a {
      width: 100% !important;

      img {
        width: 100%;
        margin-top: 10px;
      }
    }
  }
}
</style>