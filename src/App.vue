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
      <meeting-page></meeting-page>
      <h4>Jesteś zalogowany jako{{ authenticatedEmail }}</h4>
      <a @click="logMeOut()">Wyloguj</a>
      <!-- <button @click="logged = false">Wyloguj</button> -->
    </div>
    <div v-else>
      <!-- Zaloguj się e-mailem -->
      <!-- <input type="text" v-model="email" /> -->
      <!-- <button @click="logMeIn()">ZALOGUJ</button> -->
      <login-form @login="logMeIn($event)" buttonLabel="Wejdź"></login-form>
      <login-form @login="logMeIn($event)" buttonLabel="Wleć"></login-form>
      <login-form @login="logMeIn($event)"></login-form>
      <login-form
        @login="logMeIn($event)"
        :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"
      ></login-form>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import MeetingPage from "./meetings/MeetingPage";
export default {
  components: { LoginForm, MeetingPage },
  data() {
    return {
      // email: "",
      // password: "",
      authenticatedEmail: "",
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logMeIn(username) {
      this.authenticatedEmail = username;
    },
    logMeOut() {
      (this.authenticatedEmail = ""), (this.email = "");
    },
  },
};
</script>



<style>
</style>
