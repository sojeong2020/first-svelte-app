<script>
	
	import Header from './components/Header.svelte';
	import Tabs from './shared/Tabs.svelte';
	import Opps from './components/Opps.svelte';
	import CreateOppForm from './components/CreateOppForm.svelte';
	import Dashboard from './components/Dashboard.svelte';

	
	//tabs
    let items = ['Dashboard','Opportunities'];
    let activeItem ='Dashboard';

	const tabSwitch = (e) =>{
         activeItem = e.detail
     }

	 //opps
	 let opps= [
	{id:11, name: 'Picking apples', description:'Come and join picking apples!'},
    {id:12, name: 'Picking cherries', description:'Come and join picking cherries!'},
    {id:13, name: 'Picking tomatoes', description:'Come and join picking tomatoes!'},
    {id:14, name: 'Picking bananas', description:'Come and join picking bananas!'},
    {id:15, name: 'Picking grapes', description:'Come and join picking grapes!'},
    {id:16, name: 'Picking mangos', description:'Come and join picking mangos!'},

	 ]; 

	 const handleAdd = (e) =>{
		 const opp = e.detail;
		 opps = [opp, ...opps];
		 activeItem = 'Dashboard';
	 }

</script>

<Header />
<main>
	<Tabs items={items} activeItem={activeItem} on:tabchange={tabSwitch} />
	{#if activeItem === 'Dashboard'}
	<Dashboard opps={opps} />

	{:else if activeItem === 'Opportunities'}
	<Opps opps={opps} />

	<CreateOppForm on:add={handleAdd}/> 
	{/if}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

/* 	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
 */
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>