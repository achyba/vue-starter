<template>
  <div class="my-app">

    <div v-if="logged">{{email}} jesteś zalogowany
      <button @click="logOut()">Wyloguj</button>
    </div>


    <div v-else>
    Witaj w systemie do zapisów na zajęcia ^.^
    Zaloguj się e-mailem

    <input type="email" v-model="email">
    <button @click="logIn()">Zaloguj</button>
    </div>
  </div>
</template>

<script>

export default {
  data() { //stan  komponentu - data go zwraca
    return {
      email: '',
      password: '',
      logged: false,
    };
  },
  methods: {
    logIn() {
      this.logged=true;
    },
    logOut() {
      this.logged=false;
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
  background-color: pink;
  border: none;
}

button:hover{
  background-color: deeppink;
  border: none;
  border-radius: 12px;
  transition-duration: 0.4s;
}
</style>
