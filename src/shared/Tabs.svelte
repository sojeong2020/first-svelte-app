<script>
import {createEventDispatcher} from 'svelte';
const dispatch = createEventDispatcher();

export let items;
export let activeItem;
</script>

<div class="tabs">
    <ul>
        {#each items as item}
        <li on:click={()=>dispatch('tabchange',item)}>
             <!-- Events dispatched from child components can be listened to in their parent.
             Any data provided when the event was dispatched is available on the "detail" property of the event object. -->
            <div class:active ={item === activeItem}>{item}</div>
        </li>
        {/each}
    </ul>

</div>

<style>
    .tabs{
        margin-bottom: 40px;
    }
    ul{
        display: flex;
        justify-content: center;
        padding: 0;
        list-style-type: none;
    }
    li{
        margin: 0 16px;
        font-size: 18px;
        color: grey;
        cursor: pointer;
    }
    .active{
        color:brown;
        border-bottom: 2px solid brown;
        padding-bottom: 8px;
    }

</style>