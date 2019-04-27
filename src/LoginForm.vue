<template>
<div>
	<label>Zaloguj się e-mailem</label> <input type="email" v-model="email">
	<button @click="enter()">{{button-label}}</button>
</div>
</template>



<script>
export default {
	props: ['button-label'],
 data() {
     return {
         email: '',
     }
 },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
 }
}
</script>