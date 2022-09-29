
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

</script>

<ul>
    {#if index >= 1}
        <li in:fade="{{duration:400}}">Routing</li>
    {/if}
    {#if index >= 2}
        <li in:fade="{{duration:400}}">Hooks</li>
    {/if}
    {#if index >= 3}
        <li in:fade>
            Transitional App
            {#if index >= 4}
            <ul in:fade>
                <li>Server-side rendering</li>
                <li>Client-side rendering</li>
            </ul>
            {/if}
        </li>
    {/if}
</ul>