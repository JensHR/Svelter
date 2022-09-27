<script lang="ts">
    import { outer, inner } from './paths.js'
    import { fade, draw } from 'svelte/transition'
    import { expand } from './customTransition'
    import { onMount } from 'svelte';
    import { quintOut } from 'svelte/easing'

    let visible = true;

    const actionKeyListener = e => {
        if((e.key === 'a') ) {
            visible = !visible;
        } 
    }
    onMount(()=>{
        document.body.addEventListener('keyup',actionKeyListener)
        return ()=> document.body.removeEventListener("keyup",actionKeyListener)
    })
</script>

{#if visible}
    <svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
        viewBox="0 0 103 124" xml:space="preserve">
        <g out:fade="{{duration: 200}}" opacity=0.2>
            <path in:expand="{{duration: 800, delay: 1000, easing:quintOut}}" class="st0" d={outer}/>
            <path in:draw="{{duration: 1000}}" class="st1" d={inner}/>
        </g>
    </svg>
{/if}

<style type="text/css">
    svg {
        width: 35%;
        height: 100%;
    }
	.st0{
        fill: #FF3E00;
        stroke: #FF3E00;
        stroke-width: 50;
    }
	.st1{
        fill:#FFFFFF;
        stroke: #ff3e00;
        stroke-width: 1.5;
    }
    path {
        fill: white;
        opacity: 1;
    }
</style>
