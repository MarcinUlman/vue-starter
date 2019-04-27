<template>
<div id="app">

	<h1>Witaj w systemie do zapisów na zajęcia</h1>
	<div v-if="!log">
		<login-form @login="logIn($event)"></login-form>
	</div>
	<div v-else>
		<h3>Witaj {{email}}!</h3>
		<a href @click="logOut()">Wyloguj</a>
	</div>

</div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
	components: {LoginForm},
	
	data() {
		  return {
		    email: '',
		    password: '',
		    log: false
		  };
		},

		methods: {
			logIn(username){
				this.log = !this.log;
				this.email = username;
			},
			
			logOut(){
				this.log = !this.log;
				this.email = ''
			}
		}
}
</script>

<style>
</style>
