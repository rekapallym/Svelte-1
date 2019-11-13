<script>
import { onMount } from "svelte";

import Display from './Display.svelte';

let inputValue = '';
let details =[];
let data;
let isLoading = false;

// onMount(async () => {
//     const res = await fetch('http://dummy.restapiexample.com/api/v1/employees');
//     data = await res.json();
//     console.log(data)
//   });
  
function click(){

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
        });
//   .then(response => response.json())
//   .then(json => console.log(json))
//   .then(json => JSON.parse(json) )
//   .catch(error=> console.log(error))
}


</script>
<div class="row">
<p>Please Enter Employee ID</p>
<input type="text" bind:value="{inputValue}" />
<button on:click={click} >Click Me</button>
</div>

{#if isLoading}
  <p>Loading...</p>
{:else}
        <table>
        <thead>
          <tr>
              <th>Employee ID</th>
              <th>Employee Name</th>
              <th>Employee Salary</th>
          </tr>
        </thead>
        {#if details != ""}
        <tbody>
          <tr>
           <!-- {#each details as detail} -->
            <td>{details[0]}</td>
            <td>{details[1]}</td>
            <td>{details[2]}</td> 
              <!-- {/each} -->
          </tr>
        </tbody>
        {/if}
      </table>
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