<template>
  <form class="login" @submit.prevent="onSubmit">
    <div class="login__wrapper">
      <h1 class="login__wrapper--title text-left m-0">
        Desire RolePlay
      </h1>
      <p class="login__wrapper--subtitle text-left">
        Лучший проект игровых серверов за всю историю GTA V
      </p>
    </div>
    <div class="login__form text-center">
      <h2  class="login__form--title m-0">
        Авторизация
      </h2>
      <p class="login__form--subtitle text-grey">
        Если у вас уже существует аккаунт, вы можете войти в него
      </p>

      <custom-input 
        label="Логин"
        icon="fa fa-user"
        @onInput="name = $event" 
      />
      <!-- {{ $v.firstName.required }} -->
      <custom-input
        label="Пароль"
        type="password"
        icon="fa fa-lock"
        @onInput="password = $event" 
      />

      <div class="row justify-content-between">
        <label class="login__form--remember-me container text-primary">Запомнить
          <input type="checkbox" checked="checked">
          <span class="checkmark"></span>
        </label>
        <div class="login__form--forgot-password">
          <router-link to="/" class="link text-grey">
            Забыли пароль?
          </router-link>
        </div>
      </div>

      <button class="login__form--submit-btn btn btn-rounded w-100 primary">Войти</button>

      <div class="row justify-content-between">
        <div class="login__form--no-account text-grey">
          <span>Нет аккаунта?</span>
        </div>
        <div class="login__form--register">
          <router-link to="/" class="link text-primary">
            Зарегистрироваться
          </router-link>
        </div>
      </div>
    </div>
  </form>
</template>
<script lang="ts">

import { Component, Vue } from 'vue-property-decorator';
import CustomInput from '@/components/customComponents/inputComponent'; // @ is an alias to /src


/* CustomInput
label: string | required
type: string | optional | default: text
icon: string | required | only font awesome
*/
@Component({
  components: {
    CustomInput,
  },
})

export default class LoginForm extends Vue {
  name = ''
  password = ''

  onSubmit() {
    console.log({name: this.name, password: this.password})
  }
}
</script>

<style>
.container {
  display: block;
  position: relative;
  padding-left: 30px;
  cursor: pointer;
  font-size: 16px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/* Hide the browser's default checkbox */
.container input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}

/* Create a custom checkbox */
.checkmark {
  border-radius: 4px;
  position: absolute;
  top: 0;
  left: 0;
  height: 19px;
  width: 19px;
  background-color: #eee;
}

/* On mouse-over, add a grey background color */
.container:hover input ~ .checkmark {
  background-color: #ccc;
}

/* When the checkbox is checked, add a blue background */
.container input:checked ~ .checkmark {
  background-color: #0075FF;
}

/* Create the checkmark/indicator (hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

/* Show the checkmark when checked */
.container input:checked ~ .checkmark:after {
  display: block;
}

/* Style the checkmark/indicator */
.container .checkmark:after {
  left: 6px;
  top: 3px;
  width: 4px;
  height: 8px;
  border: solid white;
  border-width: 0 3px 3px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}
</style>
