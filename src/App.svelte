<svelte:window on:keydown={e => handleKeydown(e.code) } />

<div bind:this={slideshow} class="slideshow">
  <svelte:component this={order[currentIndex]}></svelte:component>
  <span class="pagination">
    {currentIndex + 1} / {order.length}
  </span>
</div>

<script>
  import Welcome from './slides/Welcome.svelte'
  import What from './slides/What.svelte'
  import Why from './slides/Why.svelte'
  import How from './slides/How.svelte'
  import Keys from './slides/Keys.svelte'
  import UseCases from './slides/UseCases.svelte'
  import Implementation from './slides/Implementation.svelte'
  import Demo from './slides/Demo.svelte'
  import Thankyou from './slides/Thankyou.svelte'
  
  const order = [
    Welcome,
    What,
    Why,
    How,
    Keys,
    UseCases,
    Implementation,
    Demo,
    Thankyou
  ]

  let slideshow
  let currentIndex = 0

  function handleKeydown (code) {
    const keys = {
      ArrowLeft: previous,
      ArrowRight: next
    }

    keys[code] && keys[code]()
  }

  function next () {
    currentIndex = currentIndex >= order.length - 1 ? currentIndex : currentIndex + 1
  }

  function previous () {
    currentIndex = currentIndex < 1 ? currentIndex : currentIndex - 1
  }
</script>