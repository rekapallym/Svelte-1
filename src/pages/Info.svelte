<script>

import { onMount } from "svelte";
import {fade, fly, slide, scale} from "svelte/transition";
let data=[];
let isLoading = false;
let inputValue =" "

onMount(async () => {
  
    const res = await fetch('http://dummy.restapiexample.com/api/v1/employees');
    data = await res.json();
    console.log(data)
    isLoading = true;
//      var i;
//    for (i = 0; i < data.length; i++) {
//         console.log( data[i]);
// }
  });

  function test(){
    if (isNaN(inputValue)){
       alert("Enter a numeric number")
    } else{
      data = data.filter(d => {
      return parseInt(d.employee_salary, 10) >= `${inputValue}`;
    })
}}

</script>




{#if isLoading == false}
  <div class="progress">
      <div class="indeterminate"></div>
  </div>
{:else}
<input type="text" bind:value="{inputValue}" >
<button class="waves-effect waves-light btn-large" type="submit" name="action" on:click={test}>Filter By Employee Salary</button>

<table class="striped">
    <thead>
          <tr>
              <th>Employee ID</th>
              <th>Employee Name</th>
              <th>Employee Salary</th>
              <th>Employee Age</th>
          </tr>
        </thead>

        <tbody transition:fade>
        {#each data as d}
          <tr >
            <td>{d.id}</td>
            <td>{d.employee_name}</td>
            <td>{d.employee_salary}</td>
            <td>{d.employee_age}</td>
          </tr>
          {/each}
         
    </tbody>
</table>

<Datepicker format=#{l}, #{F} #{j}, #{Y} bind:formattedSelected bind:dateChosen>
  <button class='custom-button'>
    {#if dateChosen} Chosen: {formattedSelected} {:else} Pick a date {/if}
  </button>
</Datepicker>

{/if}
