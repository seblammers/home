<script>
    import { fly } from 'svelte/transition'
</script>

<h1 in:fly={{ x: -200, duration: 250, delay: 500 }} >This is home.</h1>

<p>Let's see how far we get this time.</p>
