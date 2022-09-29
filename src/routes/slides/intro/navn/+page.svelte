<script lang="ts">
    import {fly} from 'svelte/transition'
</script>

<h2 in:fly="{{x: -100, duration: 300}}" >
    Svelte
</h2>
<h3 in:fly="{{x: -100, duration: 300, delay: 300}}">
    Created by Rich Harris
</h3>