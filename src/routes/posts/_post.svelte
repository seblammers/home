<script>
  import { fly } from 'svelte/transition'
  export let title
  export let date
  export let categories
</script>
  
  <h1 in:fly={{ x: -200, duration: 250, delay: 500 }} >{title}</h1>
  
  <p>Published: {date}</p>
  
  <article class="post flow">
    <slot />  
  </article>

  {#if categories.length}
    <aside class="flow">
      <h3>Posted in:</h3>
      <ul>
        {#each categories as category}
          <li>
            <a href="/posts/categories/{category}">
              {category}
            </a>
          </li>
        {/each}
      </ul>
    </aside>
  {/if}