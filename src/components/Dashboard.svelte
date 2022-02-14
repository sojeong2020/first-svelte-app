<script>
    import { Link } from "svelte-routing";

    export let opps;
    console.log(opps,"opps")
    let slicedOpps= opps.slice(0,3)
    console.log(slicedOpps,"slicedOpps")


</script>

<h2>Popular Opportunities</h2>
<div>
   
</div>


<div class="dashboard-list">
    {#each slicedOpps as opp }
    <Link to="detail/{opp.id}">
    <li>{opp.name}</li>
    </Link>
    {/each}
</div>

<style>
    .dashboard-list{
        list-style: none;
    }

</style>

