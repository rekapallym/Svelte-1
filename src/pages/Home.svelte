<script>

import Display from './Display.svelte';

let inputValue = '';
let details =[];

let isLoading = false;



  
function click(){

     if (isNaN(inputValue)){
       alert("Enter a numeric number")
    } else{
      isLoading = true;
    fetch('http://dummy.restapiexample.com/api/v1/employee/' + `${inputValue}`)
    .then(res => {
        isLoading = false;
        if(!res.ok){
            throw new Error("Failed");
        }
        return res.json();
    })
    .then(data =>{
        details = Object.values(data)
        console.log(details)
        })
    .catch(err => {
        console.log(err);
    });

    }

    
    
    
//   .then(response => response.json())
//   .then(json => console.log(json))
//   .then(json => JSON.parse(json) )
//   .catch(error=> console.log(error))
}

</script>

<style>

</style>

<div class="row">
<h6>Please Enter Employee ID</h6>
<input type="text" bind:value="{inputValue}" />
<button class="waves-effect waves-light btn-large" type="submit" name="action" on:click={click} >Submit</button>
</div>

{#if isLoading}
  <div class="progress">
      <div class="indeterminate"></div>
  </div>
{:else}
<Display {details} />
{/if}









<!-- <Display {data}/> -->
<!-- <p>{mani.employee_name}</p>
<p>{mani.id}</p> -->

<!-- {#if errOut == true}
<h1>Please Enter a Valid Employee ID</h1>
{/if} -->





 <!-- <ul>
    {#each details as detail}
      <li>{detail}</li>
    {/each}
  </ul> -->

