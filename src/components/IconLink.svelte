<script lang="ts">
    export let svg;
    export let href;
    export let size = '2rem';
</script>

<a {href} style:width={size} style:height={size}>{@html svg}</a>

<style>
    a {
        display: grid;
        place-items: center;
    }
    a:hover {
        color: #ff3e00;
    }
    a:global(svg) {
        height: 24px;
        width: 24px;
    }
</style>