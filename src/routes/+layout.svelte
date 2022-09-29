<script>
    import "../style/global.css";
    import Header from "../components/Header.svelte";
    import Footer from "../components/Footer.svelte";
</script>

<div class="root">
    <Header />
        <main class="container">
            <slot />
        </main>
    <Footer />
</div>

<style>
    .root {
        display: grid;
        grid-template-rows: auto 1fr auto;
        gap: 0;
        height: 100%;
        overflow-x: hidden; /* prevent scrollbar flickering */
        /* margin-right: calc(-1 * (100vw - 100%)); */
        max-height: 1080px;
    }
    main {
        height: 100%;
    }
</style>