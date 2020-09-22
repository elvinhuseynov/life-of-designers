<template>
  <div class="container">
    <div class="main">
      <div class="login">Login</div>
      <div class="input">
        <input type="password" v-model="pass" placeholder="Password" />
      </div>
      <div class="submit">
        <button @click="submit()">Proceed</button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      pass: '',
      data: '',
    }
  },

  methods: {
    submit() {
      axios
        .get(
          'https://portfolio-site-nuxt.firebaseio.com/adminPass/-MHVfvzzzg6UBSfYQ6uQ/pass.json'
        )
        .then((response) => {
          this.data = response.data

          if (this.pass == this.data) {
            this.$router.push('/admin/admin-page')
          } else {
            this.pass = ''
          }
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
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .login {
    font-size: 30px;
  }

  .input {
    margin-top: 20px;

    input {
      outline: 0;
      border: none;
      border-bottom: 1px solid gray;
      text-align: center;
      font-size: 20px;
    }
  }

  .submit {
    margin-top: 20px;

    button {
      background: none;
      transition: 0.4s;
      outline: none;
      font-size: 20px;
      border: 1px solid gray;
    }

    button:hover {
      transition: 0.4s;
      background-color: black;
      color: white;
    }
  }
}
</style>