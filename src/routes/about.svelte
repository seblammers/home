<script>
    import { fly } from 'svelte/transition'
</script>

<h1 in:fly={{ x: -200, duration: 250, delay: 500 }} >Hi, there!</h1>

<p>This is the about page.</p>