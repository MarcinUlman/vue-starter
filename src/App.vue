<template>
<div id="app">
	<!-- 	<div v-if="email.length  < 10">Ale masz krótki email!</div>
	<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
	<div v-else>Tw�j adres e-mail jest stanowczo zasłuugi.</div> -->

	<h1>Witaj w systemie do zapisów na zajęcia</h1>
	<div v-if="!log">
		<p>Zaloguj się e-mailem <input tyle="email" v-model="email"></p>
		<button @click="logIn()">Zaloguj</button>
	</div>
	<div v-else>
		<h3>Witaj {{email}}!</h3>
		<p @click="logOut()">Wyloguj</p>

	</div>


</div>
</template>

<script>
import "milligram";

export default {
	//definicja stanu metoda o nazwie data()
	data() {
		  return {
		    email: '',
		    password: '',
		    log: false
		  };
		},
		//zachowanie - metody
		methods: {
			logIn(){
				this.log = !this.log;
			},
			
			logOut(){
				this.log = !this.log;
				this.email = ''
			}
		}
}
</script>

<style>
#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
