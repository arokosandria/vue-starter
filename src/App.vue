<template>
<div>
<h1>Witaj w œwiecie zapisów</h1>
 
    <div v-if="isAuthenticated">
   Zalogowany jako {{email}}
   <a @click="LogMeOut()">Wyloguj</a>
    </div>
    
<div v-else>
<label>Zaloguj siê mailem</label>
<input type="text" v-model="email">
<button @click="logMeIn()">Wchodze</button>

</div>
  </div>
</template>

<script>

export default {
data() {
return {
email: '',
isAuthenticated: false
};
},
methods: {
logMeIn() {
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



