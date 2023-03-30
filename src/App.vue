<template>
  <nav>
    <router-link class="text-4xl" to="/">Contact Us</router-link>
  </nav>
  <router-view/>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body{
  background-color: rgba($color: #B2AC88, $alpha: 1.0);
  margin: 0;
  padding: 0;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #ffffff;

    &.router-link-exact-active {
      color: #ffffff;
    }
  }
}
</style>
