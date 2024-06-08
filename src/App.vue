<template>
  <nav class="fs-2">
    <router-link to="/">Home</router-link> |
    <router-link to="/juegos">Juegos</router-link>
  </nav>
  <router-view />
</template>

<style lang="scss">
#app {
  font-family: "Chakra Petch", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: hsl(255, 17%, 95%);
  background-image: url("./assets/Fondo.jpg");
  width: 100vw;
  height: 100vh;
  background-position: center center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #f0ecea;

    &.router-link-exact-active {
      color: #fcfaf8;
    }
  }
}
</style>
