 <script>
 import { Link } from "svelte-routing";

 </script>

 <nav class="teal lighten-2" role="navigation" >
    <div class="nav-wrapper">
     <div class="container">
       <Link to='/'><span class="brand-logo">Bank Of Dragons</span></Link>
       <ul id="nav-mobile" class="right hide-on-med-and-down"> 
        <li><Link to='/' >Home</Link></li>
        <li><Link to='/about'>About</Link></li>
      </ul>
     </div>
    </div>
  </nav>
        