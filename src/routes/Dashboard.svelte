<script>
    import { Link } from "svelte-routing";

    export let opps;
    console.log(opps,"opps")

</script>

<p>dashboard</p>


<div class="dashboard-list">
    {#each opps as opp }
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

