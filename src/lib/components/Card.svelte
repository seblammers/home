<script>
    export let post
    
    import { dateFormat } from '$lib/assets/js/utils'
</script>
  
<article
    class="card"
>
    <a sveltekit:prefetch href={post.path}>
    <div>
        <h3 class="title">
        {post.meta.title}
        </h3>
        <div class="more">
        <time>{dateFormat(post.meta.date)}</time>
        <div class="pill">Read More</div>
        </div>
    </div>
    </a>
</article>

<style lang="scss">
    
    .card {
        font-family: var(--accentFont);
        border-radius: var(--radius);
        border: var(--radius) solid var(--accent);
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

            .pill {
                background-color: var(--accent);
                color: var(--surface2-light);
                
            }
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

        .pill {
            color: var(--ink);
            // transition-property: color;
            // transition-duration: 0.5s;
        }
        .more {
            display: flex;
            flex-direction: row;
            align-items: center;
            justify-content: space-between;
        }
    }    
    

</style>