<template>
  <div class="wrapper">
    <router-link to="/">
      <div id="title">PyChan</div>
    </router-link>
    <div class="subPages">
      <router-link class="nav" to="/commands">Komendy</router-link>
      <router-link class="nav" to="/about">Twórcy</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar"
}
</script>

<style scoped>
.wrapper {
  height: 80px;
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
}

#title {
  font-size: 4vmin;
  text-align: center;
}

.nav {
  margin: 0 20px;
  font-size: 3vmin;
}

a {
  text-decoration: none;
}
</style>
