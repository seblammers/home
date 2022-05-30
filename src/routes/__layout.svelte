<script context="module">
    export const load = ({ url }) => {
      const currentRoute = url.pathname
  
      return {
        props: {
          currentRoute
        }
      }
    }
</script>

<script>
    import Header from '$lib/components/Header.svelte';
    import Footer from '$lib/components/Footer.svelte';
    import '$lib/styles/global.scss';
    import "@fontsource/inter/index.css";
    import { fade } from 'svelte/transition'

    export let currentRoute;

</script>
  
<Header />

{#key currentRoute}
  <main in:fade={{ duration: 250, delay: 250 }} out:fade={{ duration: 250 }}>
    <slot />
  </main>
{/key}

<Footer />