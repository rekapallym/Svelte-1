 <script>
 import { Link } from "svelte-routing";

 </script>

 <nav class="teal lighten-2" role="navigation" >
    <div class="nav-wrapper">
     <div class="container">
       <Link to='/'><span class="brand-logo">Employee Info</span></Link>
       <ul id="nav-mobile" class="right hide-on-med-and-down"> 
        <li><Link to='/' >Home</Link></li>
        <li><Link to='/info'>Info</Link></li>
      </ul>
     </div>
    </div>
  </nav>
        