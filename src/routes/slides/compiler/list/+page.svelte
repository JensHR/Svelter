<script lang="ts">
    import { onMount } from 'svelte';
    import {fade, fly, slide} from 'svelte/transition'

    let index = 0;

    const keyNavListener = e => {
        if((e.key === 'l')) {
            index++;
        } else if (e.key === 'k') {
            index--
        }
    }
    onMount(()=>{
        document.body.addEventListener('keyup',keyNavListener)
        return ()=> document.body.removeEventListener("keyup",keyNavListener)
    })

    let VDOM = 'Virtual DOM'
    let DOMS = 'DOM Surgery'
</script>

<ul>
    {#if index >= 1}
        <li in:fade="{{duration:400}}">Smaller bundles</li>
    {/if}
    {#if index >= 2}
        <li in:fade="{{duration:400}}">Low boilerplate</li>
    {/if}
    {#if index >= 3}
        <li in:fade>
            {#each VDOM as char, i}
                <span in:slide="{{duration: 2000, delay: i * 25}}" style="text-decoration:line-through">{char}</span>
            {/each}
            {#each DOMS as char, i}
                <span in:fly="{{duration: 2000, delay: 1000 + i * 25}}" >{char}</span>
            {/each}
        </li>
    {/if}
</ul>