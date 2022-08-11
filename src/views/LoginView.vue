<template>
  <main class="form-signin w-100 m-auto">
    <form @submit.stop.prevent="submit">
      <h1 class="h3 mb-3 fw-normal">Entrar</h1>
      <div class="form-floating">
        <input
          v-model="username"
          type="text"
          class="form-control"
          id="username"
          placeholder="Usuário"
        />
        <label for="username">Usuário</label>
      </div>
      <div class="form-floating">
        <input
          v-model="password"
          type="password"
          class="form-control"
          id="user-password"
          placeholder="Password"
        />
        <label for="user-password">Senha</label>
      </div>

      <button class="w-100 btn btn-lg btn-primary" type="submit">
        Sign in
      </button>
    </form>
  </main>
</template>
<script>
import axios from "axios";
import Cookie from "js-cookie";

export default {
  name: "LoginView",
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    submit() {
      axios
        .post("http://192.168.10.14:8081/login", {
          username: this.username,
          password: this.password,
        })
        .then((resp) => {
          console.log(resp.data);
          const data = resp.data;
          console.log(data.token);
          Cookie.set("_session_token", data.token);
        });
    },
  },
};
</script>
<style>
.form-signin {
  display: flex;
  align-content: center;
  justify-content: center;
  max-width: 330px;
  padding: 15px;
}

.form-signin .form-floating:focus-within {
  z-index: 2;
}

.form-signin input[type="email"] {
  margin-bottom: -1px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}

.form-signin input[type="password"] {
  margin-bottom: 10px;
  border-top-left-radius: 0;
  border-top-right-radius: 0;
}
</style>