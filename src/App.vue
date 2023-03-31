<template>
  <nav>
    <router-link class="font-semibold ml-10" to="/">Contact Us</router-link>
  </nav>
  <router-view/>
</template>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Archivo&family=Poppins:wght@600&display=swap');
#app {
  // text-align: center;
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
    color: #ffffff;
    font-size: 40px;
    font-family: 'Poppins', sans-serif;
    
    &.router-link-exact-active {
      color: #ffffff;
    }
  }
}
</style>
