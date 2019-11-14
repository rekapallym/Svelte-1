<script>
export let username='';
export let password='';

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

<div class="css"> 
<h1>This is login page</h1>
<input type="text" name="username" bind:value="{username}"> 
<input type="text" name="password" bind:value="{password}"> 
<button on:click={clic}>Login</button>
</div>

 