<template>
  <div class="my-app">

    <div v-if="authentiatedUsername.length>0">Cześć {{authentiatedUsername}}! Jesteś zalogowana/y ;)
      <button @click="logOut()">Wyloguj</button>
    </div>


    <div v-else>
      <h1>Witaj w systemie do zapisów na zajęcia ^.^</h1>
      <LoginForm @login="(username) => logMeIn(username)" buttonLabel="Zaloguj"></LoginForm>
      <LoginForm @login="(username) => logMeIn(username)" buttonLabel="Zarejestruj"></LoginForm>
      <LoginForm @login="(username) => logMeIn(username)" buttonLabel="Wyjdź"></LoginForm>
    </div>

  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},
  data() { //stan  komponentu - data go zwraca
    return {
      authentiatedUsername: '',
      password: '',
    };
  },
  methods: {
    logOut() {
      this.authentiatedUsername = '';
    },

    logMeIn(username) {
      this.authentiatedUsername = username;
    }
  }
}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: deeppink;
}
.my-app div{
  margin-top: 20px;
}
button{
  margin-left: 2px;
  background-color: rebeccapurple;
  border: none;
}

button:hover{
  background-color: deeppink;
  border: none;
  border-radius: 12px;
  transition-duration: 0.4s;
}
</style>
