<template>
  <div class="main">
    <div v-if="src1" class="img-right img">
      <img :src="src1" alt />
    </div>
    <div class="information flex">
        <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit.
            Lorem ipsum dolor, sit amet consectetur adipisicing elit.
        </p>
    </div>
    <div v-if="src2" class="img-left img">
      <img :src="src2" alt />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      src1: 'https://miro.medium.com/max/1200/1*mk1-6aYaf_Bes1E3Imhc0A.jpeg',
      src2: '',
    }
  },
}
</script>

<style lang="scss" scoped>
.main {
  display: flex;
  justify-content: space-between;

  .img {
    width: 60%;
    img {
      width: 100%;
    }
  }

  .flex {
    width: 39%;
  }
}

@media screen and (max-width: 992px) {
    .main{
        flex-direction: column;

        .img{
            width: 100%;
        }

        .flex{
            width: 100%;
        }
    }
}
</style>