<script>
    import {onMount} from "svelte";
    import {page} from '$app/stores'
    import {goto} from '$app/navigation'
    import {pageOrder} from "../routes/page-order.js";

    $: currentIndex = pageOrder.indexOf('/'+$page.routeId);
    $: next = (currentIndex < (pageOrder.length -1)) ? pageOrder[currentIndex +1] : null
    $: prev = (currentIndex > 0) ? pageOrder[currentIndex -1] : null

    const keyNavListener = e => {
        if((e.key === 'ArrowRight') && next != null) {
            goto(next)
        } else if(e.key === 'ArrowLeft' && prev != null) {
            goto(prev)
        }
    }
    onMount(()=>{
        document.body.addEventListener('keyup',keyNavListener)
        return ()=> document.body.removeEventListener("keyup",keyNavListener)
    })
</script>
<footer>
    <div class="container">
        <nav>
            {#if prev}
                <a href={prev}>prev</a>
            {:else}
                <a href='/'>home</a>
            {/if}
            <div class="right">
                {#if next}
                    <a href={next}>{currentIndex === 0 ? 'start':'next'}</a>
                {/if}
            </div>
        </nav>
    </div>
</footer>
<style>
    footer {
        position: fixed;
        bottom: 0;
    }
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0 0.5rem;
        padding: 1rem 0.25rem;
        font-size: 1.5rem;
    }
    @media (min-width: 1024px) {
        .container {
            flex-direction: row;
            
        }
    }
    .right {
        display: flex;
        gap: 1rem;
        flex-shrink: 0;
    }

    nav {
        display: flex;
        gap: 0.5rem;
        align-items: center;
        justify-content: space-between;
        flex-grow: 1;
    }
</style>