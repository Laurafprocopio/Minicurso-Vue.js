<template>
  <div class="second-column">
    <h2 class="title title-second">Formulario de Cadastro</h2>
    <p class="description description-second">ou use seu email para cadastrar</p>
    <form class="form" @submit.prevent="validateSignUp">
      <label class="label-input">
        <i class="far fa-user icon-modify"></i>
        <input type="text" v-model="signupData.name" placeholder="Nome" required />
      </label>
      <label class="label-input">
        <i class="far fa-envelope icon-modify"></i>
        <input type="email" v-model="signupData.email" placeholder="Email" required />
      </label>
      <label class="label-input">
        <i class="fas fa-lock icon-modify"></i>
        <input type="password" v-model="signupData.password" placeholder="Senha" required />
      </label>
      <button type="submit" class="btn btn-second">Cadastrar</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      signupData: {
        name: "",
        email: "",
        password: ""
      }
    };
  },
  methods: {
    validateSignUp() {
      if (!this.signupData.name || !this.signupData.email || !this.signupData.password) {
        alert("Por favor, preencha todos os campos de cadastro.");
      } else {
        alert("Cadastro realizado com sucesso!");
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
