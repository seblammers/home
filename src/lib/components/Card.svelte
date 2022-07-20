<script>
    export let post
    
    import { dateFormat } from '$lib/assets/js/utils'
</script>
  
<article
    class="card"
>
    <a sveltekit:prefetch href={post.path}>
    <div>
        <h3 class="">
        {post.meta.title}
        </h3>
        <div class="">
        <time>{dateFormat(post.meta.date)}</time>
        </div>
    </div>
    </a>
</article>

<style lang="scss">
    .card {
        border-radius: 0.15em;
        border: 1px solid;
        border-color: var(--accent);
        border: 2px solid var(--accent);
        padding: var(--space-m);
        background-color: var(--surface2-light);
        max-width: 42rem;
        
        & > a {
            text-decoration: none;

            &:hover {
                color: inherit;
            }
        }
        &:hover {
            box-shadow: 0px 0px 20px var(--accent);
            
            // -webkit-transform: translate(0,-10px);
            // transform: translate(0,-10px);
        }
        &:hover h3 {
            transform: scale(1.01) translateY(-10%);
        }
        h3:hover {
            --_p: 0%;
        }

        time {
            color: var(--ink);
        }
    }

    
</style>