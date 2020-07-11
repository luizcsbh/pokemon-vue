<template>
  <div class="login-screen__form">
     <img
      src="./../assets/logo-pixel.gif"
      alt="pokémon"
    >
    <p>Bem-vindo treinador de Pokémons</p>
    <div class="nes-field">
      <label for="name_field">Seu Nome</label>
      <input
        id="name_field"
        v-model="username"
        type="text"
        class="nes-input"
        @keyup.enter="checkPassword"
      >
    </div>
    <div class="nes-field">
      <label for="password_field">Senha</label>
      <input
        id="password_field"
        v-model="password"
        type="password"
        class="nes-input"
        @keyup.enter="checkPassword"
      >
    </div>
    <a
      class="nes-btn is-success entrar"
      @click="checkPassword"
    >
      Entrar
    </a>
    <p
      v-if="showPasswordError"
      class="nes-text is-error"
    >
      Oops, senha errada. Tente novamente!
    </p>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
import { validatePassword } from '@/utils/validatePassword'

export default {
    data: function() {
        return {
            username: '',
            password: '',
            passwordCorrect: false,
            showPasswordError: false,
        }
    },
    methods: {
        checkPassword() {
            this.passwordCorrect = validatePassword(this.password)
            if (this.passwordCorrect) {
                this.setUserLoggedIn()
                this.$router.push('/')
            } else {
                this.showPasswordError = true
            }
        },
        ...mapActions(['setUserLoggedIn']),
    },
}
</script>

<style scoped>
.login-screen__form {
    width: 500px;
    margin: 300px auto;
}
.entrar{
    height: 3em;
    width: 7em;
    display: flex;
    margin-top: 2em;
    margin-left: 40%;
}
</style>