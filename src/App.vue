<template>
<div>
<h1>Witaj w �wiecie zapis�w</h1>
 
    <div v-if="isAuthenticated">
   Zalogowany jako {{email}}
   <a href @click="LogMeOut()">Wyloguj</a>
    </div>
    
<div v-else>

<login-form @login="logMeIn($event)"></login-form>

<login-form @login="enter($event)" :button-label="'Wejd�'"></login-form>
<login-form @login="enter($event)" :button-label="'Wle�'"></login-form>
<login-form @login="enter($event)" :button-label="'Zaloguj si� jak cz�owiek'"></login-form>

</div>
  </div>
</template>

<script>
import 'milligram';
import LoginForm from "./LoginForm";
export default {
components: {LoginForm},
data() {
return {
email: '',
isAuthenticated: false
};
},
methods: {
logMeIn(username) {
 this.isAuthenticated=true;
   
  },
  logMeOut() {
  this.isAuthenticated=false;
  this.email=' ';
  }

}
}
</script>

<style>

</style>



