<script>
    import{ createEventDispatcher } from 'svelte';

    let dispatch = createEventDispatcher();

    let fields = {name:'', description:''}
    

    const submitHandler = () => {
       
        //add new opp
        
            let opp = {...fields, id: Math.random(), }
            dispatch('add', poll);
        

    }


</script>

<form on:submit|preventDefault={submitHandler}>
    <div class="form-field">
        <label for="name">Name: </label>
        <input type="text" id="name" bind:value={fields.name}>
    </div>
    <div class="form-field">
        <label for="description">Description: </label>
        <input type="text" id="description" bind:value={fields.description}>
    </div>
    <button>Add opportunity</button>

</form>

<style>

</style>