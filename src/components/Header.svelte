<script>
    import IconLink from "./IconLink.svelte";
    import svelteIcon from '../assets/Svelte_Logo.svg?raw'

</script>
<header>
    <div class="container">
        <nav>
            <IconLink svg={svelteIcon} href='/'/>
        </nav>
        <div class="right">
            Creating cool stuff fast
        </div>
    </div>
</header>
<style>
    .container {
        display: flex;
        font-size: 1.2rem;
        padding: 2rem 0;
    }
    .right {
        display: flex;
        gap: 1rem;
        flex-shrink: 0;
    }
    nav {
        display: flex;
        flex-direction: column;
        justify-content: center;
        gap: 0.5rem 0;
        flex-grow: 1;
    }
</style>