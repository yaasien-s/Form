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
  background-image: url(./assets/bg/Web\ Page.png);
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  margin: 0;
  padding: 20px;

  @media (max-width:1023px) {
    background-position: right;
  }
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
