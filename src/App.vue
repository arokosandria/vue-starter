<template>
<div>
<h1>Witaj w œwiecie zapisów</h1>
 
    <div v-if="isAuthenticated">
   Zalogowany jako {{email}}
   <a href @click="LogMeOut()">Wyloguj</a>
    </div>
    
<div v-else>

<login-form @login="logMeIn($event)"></login-form>

<login-form @login="enter($event)" :button-label="'WejdŸ'"></login-form>
<login-form @login="enter($event)" :button-label="'Wleæ'"></login-form>
<login-form @login="enter($event)" :button-label="'Zaloguj siê jak cz³owiek'"></login-form>

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



