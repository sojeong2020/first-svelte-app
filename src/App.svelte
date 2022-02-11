<script>
import { Router, Link, Route} from "svelte-routing";
import Home from "./routes/Home.svelte";	
import Dashboard from "./routes/Dashboard.svelte";
import Opps from "./routes/Opps.svelte";
import OppDetail from "./routes/OppDetail.svelte";	

export let url = "";

</script>

<Router {url} >
	<nav>
		<Link to="/">Home</Link>
        <Link to="dashboard">Dashboard</Link>
		<Link to="opps">Opportunities</Link>
	</nav>
	<div>
		<Route path="/"><Home /></Route>
		<Route path="dashboard"><Dashboard /></Route>
		<Route path="opps"><Opps /></Route>
		<Route path="oppDetail"><OppDetail /></Route>
    </div>

</Router>	
	



<main>

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	/* h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	} */
 
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>