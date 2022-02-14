<script>
    import {createEventDispatcher} from 'svelte';
    import { Link } from "svelte-routing";
    import OppDetail from "./OppDetail.svelte";
    export let opps =[]

    const dispatch = createEventDispatcher()

     const handleDelete=(oppId)=>{
         console.log(oppId,"oppId")
         dispatch('delete-opp', oppId)
     }
     
     let newName = '';
     let newOpp = '';

    function handleAdd(){
        opps = [...opps, {id: Math.max(...opps.map(t => t.id)) + 1, name: newName, description: newOpp}]
       
        console.log(opps,"opps!!!!")
        dispatch('add-opp', opps)


    }
     
</script>

<h2>List of opps</h2>

<div class="opp-list">
{#each opps as opp  }
<Link to="detail/{opp.id}">
    <OppDetail opp={opp}/>
</Link>
<button class="delete" on:click={()=> handleDelete(opp.id)}>
    Delete
</button>

{/each}

<form on:submit|preventDefault class="add-opp">
 <label for="new-name">Name</label>
 <input bind:value={newName} type="text" id="new-name" autocomplete="off"  />

 <label for="new-opp">Opportunity</label>
 <input bind:value={newOpp} type="text" id="new-opp" autocomplete="off"  />

<button on:click={handleAdd}>Add</button>
</form>

</div>

<style>
    .opp-list{
        list-style: none;
    }
    .add-opp {
        margin-top: 20px;
    }

</style>

