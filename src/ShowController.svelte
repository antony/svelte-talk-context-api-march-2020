<svelte:window on:keydown={e => handleKeydown(e.code) } />

<script>
  import { getContext, onDestroy } from 'svelte'
  import key from './key.js'

  const bcast = new BroadcastChannel('svelte-present')
  const store = getContext(key)

  function handleKeydown (code) {
    const keys = {
      ArrowLeft: () => bcast.postMessage('previous'),
      ArrowRight: () => bcast.postMessage('next'),
      ArrowUp: () => $store.full = !$store.full,
      ArrowDown: () => {
        $store.index = 0
        window.open(window.location.href)
      }
    }

    keys[code] && keys[code]()
  }

  onDestroy(() => {
    bcast.close()
  })
</script>