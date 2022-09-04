<script>
    export let open = false;
      import { slide } from 'svelte/transition';
      const handleClick = () => open = !open
  </script>
  
  <div class="accordion">
      <div class="header" on:click={handleClick} >
          <div class="text">
              <b>Show me the code</b>
          </div>
          <div class="tap">
              {#if open}
              tap me to hide details
              {:else}
              tap me to show details
              {/if}
          </div>
  </div>
          {#if open}
      <div class="details" transition:slide>
          <slot/>
      </div>
      {/if}
  </div>
  
  <style>
      div.accordion {
          margin: 1rem 0;
          font-family: var(--accentFont);
      }
      
      div.header {
          display: flex;
          flex-direction: column;
          width:100%;
          background: #ddd;
          padding: 1rem;
      }
      
      div.header:hover {
      cursor: pointer;
      }
      div.header .text {
          flex: 1;
          margin-right: 5px;
      }
  
      div.details {
          /* background-color: #cecece; */
          padding: 1rem;
      }
      
      .tap {
          font-style: italic;
      }
  </style>
  