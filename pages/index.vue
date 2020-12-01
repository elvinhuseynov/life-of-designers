<template>
  <div class="main">
    <div class="box-model container" v-for="(image, index) in images" :key="index">
      <div class="little-images image-div">
        <div class="img">
          <img :src="image.firstImgUrl" alt />
          <span class="img-info">{{ image.firstImgTitle }}</span>
        </div>
        <div class="img">
          <img :src="image.scndImgUrl" alt />
          <span class="img-info">{{ image.scndImgTitle }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      images: [],
    }
  },
  created() {
    axios
      .get('https://portfolio-nuxt.firebaseio.com/homePageImages.json')
      .then((response) => {
        let data = response.data
        for (let key in data) {
          this.images.unshift({ ...data[key], id: key })
        }
      })
      .catch((error) => console.error(error))
  },
}
</script>

<style lang="scss" scoped>
.main {
  width: 100%;

  .box-model {

    width: 100%;
    margin-top: 7px;

    .little-images {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      width: 100%;

      .img {
        width: 49.7%;

        img {
          position: relative;
          width: 100%;
          max-height: 40vh;
        }
      }
    }
  }
}

.img,
.image {
  position: relative;

  span {
    display: none;
    position: absolute;
    top: 70%;
    right: 38%;
  }
}

.img:hover,
.image:hover {
  img {
    opacity: 0.2;
  }

  span {
    display: block;
    font-weight: 700;
    font-size: 20px;
  }
}

@media screen and (max-width: 992px) {
.image-div{
  display: flex !important;
  width: 100%;
  flex-direction: column !important;
  
  .img{
    width: 100% !important;
    z-index: 0;
  }
}

}
</style>
