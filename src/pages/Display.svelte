<script>
import {fade, fly, slide, scale} from "svelte/transition";
export let details;

</script>
 {#if details != ""}
        <table transition:fade>
        <thead>
          <tr>
              <th>Employee ID</th>
              <th>Employee Name</th>
              <th>Employee Salary</th>
          </tr>
        </thead>
       
        <tbody  >
          <tr>
           <!-- {#each details as detail} -->
            <td>{details[0]}</td>
            <td>{details[1]}</td>
            <td>{details[2]}</td> 
              <!-- {/each} -->
          </tr>
        </tbody>
        
      </table>
      {/if}

