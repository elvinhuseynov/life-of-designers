<template>
  <div class="main container">
    <div class="box">
      <img :src="dataArr.image" alt />
    </div>
    <div class="box">
      <p>{{ dataArr.info }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      dataArr: {
        image: '',
        info: '',
      },
      tester: [],
    }
  },
  created() {
    axios
      .get('https://portfolio-nuxt.firebaseio.com/aboutPage.json')
      .then((response) => {
        let data = response.data

        for (let key in data) {
          this.tester.push({ ...data[key], id: key })
          this.start()
        }
      })
      .catch((error) => console.error(error))
  },
  methods: {
    start() {
      for (let i in this.tester) {
        if (this.tester[i].name === 'Murad') {
          this.dataArr.image = this.tester[i].image
          this.dataArr.info = this.tester[i].info
        }
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.main {
  display: flex;
  width: 100%;
  flex-direction: row;
  justify-content: space-between;

  .box {
    width: 48%;

    img {
      width: 100% !important;
    }
  }
}
</style>