<template>
  <div class="card text-center">
    <div class="card-header">Detalhes de Usuario</div>
    <div class="card-body">
      <p class="card-text">Id:{{usuarios.id}}</p>
      <p class="card-text">Nome: {{usuarios.name}}</p>
      <p class="card-text">Email: {{usuarios.email}}</p>
      <p class="card-text">Biografia: {{usuarios.bio}}</p>
      <a href="/user" class="btn btn-primary">Voltar</a>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "User",
  props: {
    msg: String
  },
  data() {
    return {
      usuarios: null
    };
  },
  mounted() {
    axios
      .get("https://www.mocky.io/v2/5ebdbed93100008e00c5cd2d")
      .then(
        response =>
          (this.usuarios = response.data.results.find(
            user => user.id == this.$route.params.id
          ))
      );
  }
};
</script>

