<script>
    export let opps =[];

</script>

<div class="opp-list">
    {#each opps as opp (opp.id)}
    <div>
    <li>{opp.name}</li>
    </div>
    {/each}

</div>

<style>
    li {
        list-style: none;
        padding:5px;
    
    }
    
</style>