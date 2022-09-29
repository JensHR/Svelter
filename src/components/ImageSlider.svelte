<script lang="ts">
    import { onMount } from "svelte";

    export let images: string[];
    

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

<img src={images[index]} alt="Example Svelte code showing animated text component">

