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
    import Nav from '$lib/components/Nav.svelte';
    import Footer from '$lib/components/Footer.svelte';
    import '$lib/styles/global.scss';
    import "@fontsource/inter/400.css";
    import "@fontsource/inter/500.css";
    import "@fontsource/inter/700.css";
    import "@fontsource/inter/900.css";
    import { fade, fly } from 'svelte/transition'

    export let currentRoute;

</script>
  
<div class="layout">
  <Nav />

  {#key currentRoute}
    <main 
      in:fly={{ y: 100, duration: 800, delay: 250 }} 
      out:fade={{ duration: 250 }}
      class="flow"
      >
      <slot />
    </main>
  {/key}

  <Footer />
</div>
