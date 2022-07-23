<script>
    import { fly } from 'svelte/transition'
</script>

<h1 in:fly={{ x: -200, duration: 800, delay: 150 }} >
    <slot></slot>
</h1>