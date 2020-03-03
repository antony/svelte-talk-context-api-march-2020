<ShowController />

{#if $store.full}
<Slideshow bind:this={slideshow} />
{:else}
<div class="speaker">
  <div class="deck pane">
    <Slideshow bind:this={slideshow} />
  </div>
  <div class="note pane">
    <Notes />
  </div>
</div>
{/if}

<script>
  import { setContext, onDestroy } from 'svelte'
  import { writable } from 'svelte/store'
  import key from './key.js'
  import slides from './slides/slides.js'

  import ShowController from './ShowController.svelte'
  import Slideshow from './Slideshow.svelte'
  import Notes from './Notes.svelte'

  const store = writable({
    full: true,
    index: 0,
    slides
  })

  setContext(key, store)

  let slideshow

</script>

<style>
  .speaker {
    display: flex;
    justify-content: space-evenly;
    width: 100%;
  }

  .pane {
    display: flex;
    width: 50%;
    box-sizing: border-box;
  }

  .deck {
  }
</style>