<div class="slide alt4">
  <h4>How?</h4>

  <h5>Entire API in two methods:</h5>

  <pre>
    <span class="component-name">Ancestor.svelte</span>
    set(key, 'some data')
  </pre>

  <pre>
    <span class="component-name">Descendent.svelte</span>
    get(key)
  </pre>
</div>

<ul class="notes">
  <li>A-la Svelte - small learning curve</li>
  <li>Set, unique key, any data</li>
  <li>Get, same key</li>
  <li>Not reactive by default - if you change the data, consumers won't update</li>
  <li>Want Reactivity? Put something reactive like a store inside it</li>
</ul>