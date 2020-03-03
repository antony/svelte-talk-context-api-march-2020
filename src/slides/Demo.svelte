<div class="slide columns alt0" on:keydown|stopPropagation>
  <div>
    <div class="grandparent hierarchy">
      <span>Grandparent.svelte</span>
      <div class="parent hierarchy">
        <span>Parent.svelte</span>
        <div class="child hierarchy">
          <span>Child.svelte</span>
          <h1>Hello, Foo</h1>
        </div>
      </div>
    </div>
  </div>
  <div>
    <pre>
<span class="component-name">Grandparent.svelte</span>
<span>{componentA.trim()}</span>
    </pre>
    <pre>
<span class="component-name">Parent.svelte</span>
<span>{componentB.trim()}</span>
    </pre>
    <pre>
<span class="component-name">Child.svelte</span>
<span>{componentC.trim()}</span>
    </pre>
  </div>
</div>

<script>
  const componentA = `<script>
  import key from './my-context.js'
  import { setContext } from 'svelte'
  import { writable } from 'svelte/store'

  let myStore = writable({ name: 'Foo' })
  setContext(key, { myStore })
<\/script>
`

  const componentB = `<script>
...
<\/script>
  `

  const componentC = `<script>
  import key from './my-context.js'
  import { getContext } from 'svelte'

  const { myStore } = getContext(key)
<\/script>

<h1>Hello {$myStore.name}</h1>
`
</script>

<style>
  pre {
    font-size: 2.2vh;
    padding: 1vh 0;
    text-align: left;
    margin: 0;
  }

  .hierarchy span {
    font-size: 2.6vh;
  }

  .hierarchy {
    box-sizing: border-box;
    padding: 4vh 4vw;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .grandparent, .child {
    background-color: #606060;
    color: #D6ED17;
  }

  .parent {
    background-color: #D6ED17;
    color: #606060;
  }

  .child h1 {
    font-size: 4vh;
    height: 100%;
    padding-top: 150%;
    color: #FB0048;
  }
</style>