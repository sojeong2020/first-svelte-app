<script>
import { Router, Link, Route} from "svelte-routing";
import { component_subscribe } from "svelte/internal";
import Dashboard from "./routes/Dashboard.svelte";
import Opps from "./routes/Opps.svelte";
import OppDetail from "./routes/OppDetail.svelte";


export let url = "";

 let opps=[
	{id:11, name: 'Picking apples', description:'Come and join picking apples!'},
    {id:12, name: 'Picking cherries', description:'Come and join picking cherries!'},
    {id:13, name: 'Picking tomatoes', description:'Come and join picking tomatoes!'},
    {id:14, name: 'Picking bananas', description:'Come and join picking bananas!'},
    {id:15, name: 'Picking grapes', description:'Come and join picking grapes!'},
    {id:16, name: 'Picking mangos', description:'Come and join picking mangos!'},

]; 

</script>



<Router {url} >
	<div>
		<h1>Svelte Opportunity</h1>
	</div>
	
	<nav>
		<div class="link"><Link to="dashboard">Dashboard</Link></div>
		<div class="link"><Link to="opps">Opportunities</Link></div>

    </nav>
	
	<div>
		<Route path="dashboard" ><Dashboard opps={opps}/></Route>
		<Route path="opps" ><Opps opps={opps} /></Route > 
		<Route path="oppDetail/:id" ><OppDetail opps={opps} /></Route > 

		<!-- <Route path="dashboard" component={Dashboard} />
		<Route path="opps" component={Opps} /> -->
    </div>

</Router>	
	

<style>
nav .link {
  padding: 1rem;
  text-decoration: none;
  margin: 10px 20px;
  
  display: inline-block;
  background-color: #e8e8e8;
  color: #3d3d3d;
  border-radius: 4px;
}

nav .link:hover {
  color: white;
  background-color: #a8def5;
}


</style>