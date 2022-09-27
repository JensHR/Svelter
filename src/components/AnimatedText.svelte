<script lang="ts">
    import { fly, fade } from 'svelte/transition'
    export let letterDelay = 50;
    export let word = 'svelte';
</script>

<div class="centered" out:fly="{{y: -20, duration:800}}">
    {#each word as char, i}
        <span in:fade="{{delay: 200 + i * letterDelay, duration: 800}}">{char}</span>
    {/each}
</div>

<style>
    .centered {
        font-size: 10vw;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%,-50%);
        font-family: 'Overpass';
        letter-spacing: 0.12em;
        color: #676778;
        font-weight: 400;
    }
</style>