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
  background-size: 100% 100%;
  padding: 218px 504px 216px 483px;
  height: 100vh;
  box-sizing: border-box;
}
</style>

