<script>
	import 'node_modules/materialize-css/dist/css/materialize.min.css';
	import 'node_modules/materialize-css/dist/css/materialize.min.js';

	let username='';
    let password='';
	

	import { Router, Link, Route } from "svelte-routing";

	import Navbar from './layout/Navbar.svelte';
	import Home from './pages/Home.svelte';
	import Info from './pages/Info.svelte';
	// import Login from './pages/Login.svelte';

	function clic(){
    console.log(username);
    console.log(password);
}
	
	
</script>

<style>

.css{
    background-color: aqua;
}
</style>

<Router>
<!-- {#if username !="mani" && password !="zeze"}
<Route path='/'> 
<div class="css"> 
<h1>This is login page</h1>
<input type="text" name="username" bind:value="{username}"> 
<input type="text" name="password" bind:value="{password}"> 
<button on:click={clic}>Login</button>
</div>
</Route>
{:else} -->
<Navbar />
<div class="container" >
<Route path="/" component="{Home}" />
<Route path="/info" component="{Info}" />
</div>
<!-- {/if} -->

</Router>
