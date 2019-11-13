<script>
import { onMount } from "svelte";
let inputValue = '';
let mani={id: "96288", employee_name: "", employee_salary: "57610", employee_age: "81", profile_image: ""};

export let data={};

onMount(async () => {
    const res = await fetch('http://dummy.restapiexample.com/api/v1/employees');
    data = await res.json();
    console.log(data)
  });
  
function click(){
    if(inputValue >= 96288){
    fetch('http://dummy.restapiexample.com/api/v1/employee/' + `${inputValue}`)
  .then(response => response.json())
  .then(json => console.log(json))
  .then(json => mani=json)
  .catch(error=> console.log(error))
    }
}
function cl(){
console.log(mani);
}

</script>
<div class="row">
<p>Please Enter Employee ID</p>
<input type="text" bind:value="{inputValue}" />
<button on:click={click} >Click Me</button>
<button on:click={cl} >zeze</button>
</div>
<p>{mani.employee_name}</p>
<p>{mani.id}</p>

<!-- {#if errOut == true}
<h1>Please Enter a Valid Employee ID</h1>
{/if} -->
<!-- 
      <table>
        <thead>
          <tr>
              <th>Employee ID</th>
              <th>Employee Name</th>
              <th>Employee Salary</th>
          </tr>
        </thead>

        <tbody>
          <tr>
            <td>{data[0]}</td>
            <td>Eclair</td>
            <td>$0.87</td>
          </tr>
          <tr>
            <td>Alan</td>
            <td>Jellybean</td>
            <td>$3.76</td>
          </tr>
          <tr>
            <td>Jonathan</td>
            <td>Lollipop</td>
            <td>$7.00</td>
          </tr>
        </tbody>
      </table> -->
