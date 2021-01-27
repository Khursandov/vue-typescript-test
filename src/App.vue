<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script lang="ts">
import('@/assets/app.scss') 

</script>

<style lang="scss">
body {
  margin: 0;
  width: 100%;
  height: 100vh;
}
#app {
  font-family: Inter;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  height: 100vh;
}

// #nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }
</style>
