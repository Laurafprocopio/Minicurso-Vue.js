<template>
  <div class="second-column">
    <h2 class="title title-second">Login</h2>
    <p class="description description-second">ou use seu email para logar:</p>
    <form class="form" @submit.prevent="validateLogin">
      <label class="label-input">
        <i class="far fa-envelope icon-modify"></i>
        <input type="email" v-model="loginData.email" placeholder="Email" required />
      </label>
      <label class="label-input">
        <i class="fas fa-lock icon-modify"></i>
        <input type="password" v-model="loginData.password" placeholder="Senha" required />
      </label>
      <a class="password" href="#">Esqueci Senha</a>
      <button type="submit" class="btn btn-second">Login</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loginData: {
        email: "",
        password: ""
      }
    };
  },
  methods: {
    validateLogin() {
      if (!this.loginData.email || !this.loginData.password) {
        alert("Por favor, preencha todos os campos de login.");
      } else {
        alert("Login realizado com sucesso!");
      }
    }
  }
};
</script>

<style scoped>
.second-column {
  width: 60%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
