<script>
  import Hamburger from './Hamburger.svelte'
  import MainNav from './MainNav.svelte'
  import { isMenuOpen } from '$lib/assets/js/store'

  const skipToContent = () => {
    const main = document.querySelector('main');
    main.focus();
  }
</script>

<header>
  <a on:click|preventDefault={skipToContent} class="skip-to-content-link" href="#main">
    Skip to main content
  </a>

  <a href="/" class="site-title">
    Home
  </a>

  <Hamburger />
  <MainNav />
</header>