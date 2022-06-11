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
    import "@fontsource/inter/400.css";
    import "@fontsource/inter/500.css";
    import "@fontsource/inter/700.css";
    import "@fontsource/inter/900.css";
    import { fade } from 'svelte/transition'

    export let currentRoute;

</script>
  
<div class="layout">
  <Header />

  {#key currentRoute}
    <main 
      in:fade={{ duration: 250, delay: 500 }} 
      out:fade={{ duration: 250 }}
      class="flow"
      >
      <slot />
    </main>
  {/key}

  <Footer />
</div>
