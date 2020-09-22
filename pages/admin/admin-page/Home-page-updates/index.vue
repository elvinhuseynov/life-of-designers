<template>
  <div class="main container">
    <div class="picture">
      <input
        type="text"
        v-model="image.firstImgUrl"
        placeholder="Enter first small sized picture's URL"
      />
      <input type="text" v-model="image.firstImgTitle" placeholder="Enter title of picture" />
    </div>

    <div class="picture">
      <input
        type="text"
        v-model="image.scndImgUrl"
        placeholder="Enter second small sized picture's URL"
      />
      <input type="text" v-model="image.scndImgTitle" placeholder="Enter title of picture" />
    </div>

    <div class>
      <button type="button" @click="submit" class="button">Submit</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      image: {
        firstImgUrl: '',
        firstImgTitle: '',
        scndImgUrl: '',
        scndImgTitle: '',
      },
    }
  },

  methods: {
    submit() {
      axios
        .post(
          'https://portfolio-site-nuxt.firebaseio.com/homePageImages.json',
          {
            ...this.image,
          }
        )
        .then((response) => {
          console.log(response)
          this.image = {}
        })
        .catch((error) => {
          console.error(error)
        })
    },
  },
}
</script>

<style lang="scss" scoped>
.main {
  display: flex;
  width: 100%;
  align-items: center;
  flex-direction: column;
  justify-content: center;

  .picture {
    display: flex;
    flex-direction: column;
    margin-top: 20px;
    width: 60%;
    align-items: center;

    input {
      margin-top: 20px;
      outline: none;
      width: 70%;
      text-align: center;
      border: none;
      font-size: 20px;
      border-bottom: 1px solid gray;
    }
  }

  .button {
    outline: none;
    margin-top: 27px;
    background: none;
    border: 1px solid gray;
    width: 129px;
    height: 41px;
    letter-spacing: 2px;
    transition: 0.3s;
  }

  .button:hover {
    background: black;
    color: white;
    width: 149px;
    transition: 0.3s;
  }
}
</style>