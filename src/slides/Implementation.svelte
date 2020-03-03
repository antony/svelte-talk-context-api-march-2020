<div class="slide alt1">
  <h4>Implementation</h4>

  <ul>
    <li>Get the context key</li>
    <li>Create your data / stores / etc</li>
    <li>Import `setContext/getContext` from `svelte` package</li>
    <li>* Put your data into the context with `setContext`</li>
    <li>Get your data from the context with `getContext`</li>
  </ul>

  <blockquote>
    * You can only put things into the context at component initialisation
  </blockquote>
</div>

<ul class="notes">
  <li>You can add a hash full of data, functions, or just primitives</li>
  <li>Put data into the context, in the parent</li>
  <li>Get data from the context, in the children</li>
  <li>Only put things into context during its creation</li>
</ul>
