<script lang="ts">
    import {fly, slide} from 'svelte/transition'
    import {backIn} from 'svelte/easing'

    let VDOM = 'Virtual DOM'
    let DOMS = 'DOM Surgery'

</script>

<h2>
    Svelte 
</h2>
<h3>
    Created by Rich Harris
</h3>
<p>
    Open source
</p>
<a href="https://github.com/sveltejs/svelte"><p>github.com/sveltejs/svelte</p></a>
<h4 in:fly="{{x: -100, duration: 300}}" >Svelte 3 (Compiler)</h4>
    

