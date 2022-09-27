<script>
    import LogoAnimation from "../components/animated-logo/LogoAnimation.svelte";

   
</script>
<div class="wrapper">
    <div class="center">
        <LogoAnimation/>
    </div>
</div>
<style>
    .wrapper {
        height: 100%;
        overflow: hidden;
    }
    .center {
        height: 100%;
        display: grid;
        place-items: center;
    }
</style>