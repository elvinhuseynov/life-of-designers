<template>
  <div class="header container">
    <h2 class="logo">Life of Designers</h2>
    <input type="checkbox" id="chk" />
    <label for="chk" class="show-menu-btn">
      <client-only>
        <unicon name="ellipsis-h" fill="red"></unicon>
      </client-only>
    </label>

    <ul class="menu">
      <nuxt-link to="/">Home</nuxt-link>
      <nuxt-link to="/about">About us</nuxt-link>
      <a href="#">Contact</a>
      <nuxt-link to="/admin">Admin</nuxt-link>
      <label for="chk" class="hide-menu-btn">
        <client-only>
          <unicon name="ellipsis-h" fill="limegreen"></unicon>
        </client-only>
      </label>
    </ul>

    <hr class="hr" />
  </div>
</template>

<script>
export default {}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:ital,wght@1,300&display=swap');

* {
  margin: 0;
  padding: 0;
  font-family: 'Josefin Sans', sans-serif;
}
.header {
  height: 100px;
  padding: 0 20px;
  color: #5fadce;
}
.logo {
  line-height: 100px;
  float: left;
}

.menu {
  float: right;
  line-height: 100px;
}
.menu a {
  color: #6d98db;
  text-decoration: none;
  padding: 0 20px;
  border-bottom: 1px solid transparent;
  transition: 1s;
}
.show-menu-btn,
.hide-menu-btn {
  transition: 0.4s;
  font-size: 30px;
  cursor: pointer;
  display: none;
}
.show-menu-btn {
  float: right;
}
.show-menu-btn i {
  line-height: 100px;
}
.menu a:hover,
.show-menu-btn:hover,
.hide-menu-btn:hover {
  color: #3498db;
}

#chk {
  position: absolute;
  visibility: hidden;
  z-index: -1111;
}

a:hover {
  border-bottom: 1px solid black;
  transition: 1s;
}
.hr {
  position: absolute;
  top: 75px;
  left: 9.2%;
  right: 0;
  width: 80%;
}
@media screen and (max-width: 992px) {
  .show-menu-btn,
  .hide-menu-btn {
    display: block;
  }

  .show-menu-btn {
    margin-top: 25px;
  }
  .menu {
    z-index: 111;
    position: fixed;
    width: 100%;
    height: 100vh;
    background: #333;
    right: -100%;
    top: 0;
    text-align: center;
    padding: 80px 0;
    line-height: normal;
    transition: 0.7s;
  }
  .menu a {
    display: block;
    padding: 20px;
  }
  .hide-menu-btn {
    position: absolute;
    top: 30px;
    right: 30px;
  }
  #chk:checked ~ .menu {
    right: 0;
  }
}
</style>