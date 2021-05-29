<template>
  <div>
    <!-- <h1>Twój e-mail to {{ email }}</h1>
    <input type="text" v-model="email" />
    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div> -->

    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="authenticatedEmail != ''">
      <div>Witaj {{ email }}!</div>
      <div>
        <a @click="logMeOut()">Wyloguj</a>
        <!-- <button @click="logged = false">Wyloguj</button> -->
      </div>
    </div>
    <div v-else>
      Zaloguj się e-mailem
      <input type="text" v-model="email" />
      <button @click="logMeIn()">ZALOGUJ</button>
    </div>
  </div>
</template>

<script>
import "milligram";
export default {
  data() {
    return {
      email: "",
      password: "",
      authenticatedEmail: "",
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logMeIn() {
      this.authenticatedEmail = this.email;
    },
    logMeOut() {
      (this.authenticatedEmail = ""), (this.email = "");
    },
  },
};
</script>



<style>
</style>
