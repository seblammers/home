<script context="module">
    export const load = async ({ fetch }) => {
      const posts = await fetch('/api/posts.json')
      const allPosts = await posts.json()
    
      return {
        props: {
          posts: allPosts
        }
      }
    }
</script>

<script>
    export let posts
    import { fly } from 'svelte/transition'
  </script>
  
<h1 in:fly={{ x: -200, duration: 250, delay: 500 }} >Posts</h1>
<p>This is where I list the stuff.</p>

<article class="flow">
  <ul class="flow">
    {#each posts as post}
      <li>
        <h3>
          <a href={post.path}>
            {post.meta.title}
          </a>
        </h3>
        Published {post.meta.date}
      </li>
    {/each}
  </ul>
</article>
