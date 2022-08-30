<script>
  import { navItems, siteAuthor } from '$lib/config';
  import { navigating, page } from '$app/stores';

  $: isActive = (url) => $page.url.pathname.includes(url);
</script>

<footer>
  <p>This site does not track you. Like at all.</p> 
  
  <p>&copy; {new Date().getFullYear()} {siteAuthor}</p>

  <!-- <div class="links">
    {#each navItems as page, i (i)}
        <a
            href={page.route}
            class:active={isActive(`${page.route}`)}>
            {page.title}
        </a>
    {/each}
</div> -->
</footer>

<style lang="scss">
  footer {
  background: var(--ink);
  color: var(--surface2-light);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--space-m) var(--space-m);

  p {
    margin: 0;
    font-size: var(--step-0);
  }
}
//   .links {
//     margin: 0px auto;
//     display: flex;
//     flex-direction: column;
//     gap: var(--space-s);
//     a {
//         font-size: var(--step-1);
//         border-width: 2px;
//         // border: none;
//     }
// }
</style>