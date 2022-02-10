<script>
	import Header from './components/Header.svelte';
	import Tabs from './shared/Tabs.svelte';

	//tabs
    let items = ['Dashboard','Opportunities'];
    let activeItem ='Dashboard';
	
	const tabSwitch = (e) =>{
         activeItem = e.detail
		 console.log(activeItem)
     }

</script>

<Header />
<main>
	<Tabs items={items} activeItem={activeItem} on:tabchange={tabSwitch} />
	{#if activeItem === 'Dashboard'}
	<p>top opps</p>
	{:else if activeItem === 'Opportunities'}
	<p>List of opps</p>
	{/if}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>