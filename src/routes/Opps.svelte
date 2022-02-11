<script>
    import { Link } from "svelte-routing";
    import OppDetail from "./OppDetail.svelte";
    export let opps;
    console.log(opps,"opps")

</script>

<h2>List of opps</h2>

<div class="opp-list">
{#each opps as opp }
<Link to="detail/{opp.id}">
<li>{opp.name}</li>
</Link>
{/each}
</div>
<OppDetail />

<style>
    .opp-list{
        list-style: none;
    }

</style>

