<template>
  <div :class="bodyClass">
    <div class="container">
      <div class="content">
        <div class="first-column">
          <h2 class="title title-primary">Atividade 01</h2>
          <p class="description description-primary">para a primeira atividade do curso de vue.js</p>
          <p class="description description-primary">preparamos este formulário de cadastro</p>
          <button id="signin" class="btn btn-primary" @click="showSignIn">Login</button>
          <button id="signup" class="btn btn-primary" @click="showSignUp">Cadastrar</button>
        </div>

        <!-- Exibe o componente de login ou cadastro -->
        <UserSignup v-if="isSignUp" />
        <UserLogin v-if="isSignIn" />
      </div>
    </div>
  </div>
</template>

<script>
import UserLogin from './components/UserLogin.vue';
import UserSignup from './components/UserSignup.vue';

export default {
  components: {
    UserLogin,
    UserSignup
  },
  data() {
    return {
      isSignIn: true,  // Exibe o formulário de login inicialmente
      isSignUp: false  // Controla a exibição do formulário de cadastro
    };
  },
  computed: {
    // Computa a classe CSS com base no estado atual (sign in ou sign up)
    bodyClass() {
      return this.isSignIn ? 'sign-in-js' : 'sign-up-js';
    }
  },
  methods: {
    showSignIn() {
      this.isSignIn = true;
      this.isSignUp = false;
    },
    showSignUp() {
      this.isSignIn = false;
      this.isSignUp = true;
    }
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Open+Sans:300,400,700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Open Sans', sans-serif;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #ecf0f1;
}

.content {
  background-color: #fff;
  border-radius: 15px;
  width: 960px;
  padding: 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
}

.title {
  font-size: 28px;
  font-weight: bold;
  text-transform: capitalize;
}

.title-primary {
  color: #fff;
}

.description {
  font-size: 14px;
  font-weight: 300;
  line-height: 30px;
}

.btn {
  border-radius: 15px;
  text-transform: uppercase;
  color: #fff;
  font-size: 10px;
  padding: 10px 50px;
  cursor: pointer;
  font-weight: bold;
  width: 150px;
  align-self: center;
  border: none;
  margin-top: 1rem;
}

.btn-primary {
  background-color: transparent;
  border: 1px solid #fff;
  transition: background-color .5s;
}

.btn-primary:hover {
  background-color: #fff;
  color: #58af9b;
}
</style>
