<template>
  <div class="login-bg">
    <login-form />
  </div>
</template>
<script lang="ts">

import('@/assets/pages/login.scss') 
import { Component, Vue } from 'vue-property-decorator';
import LoginForm from '@/components/Login/loginForm'; // @ is an alias to /src

@Component({
  components: {
    LoginForm,
  },
})

export default class Home extends Vue {
}
</script>

<style>
.login-bg {
  background: url('../assets/Images/Login/image2.png') no-repeat;
  background-size: cover;
  background-position: center center;
  height: 100vh;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>

