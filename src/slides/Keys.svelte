<div class="slide alt1">
  <h4>Context Key</h4>

  <blockquote>
    A context key is designed to be unique, to prevent conflicts between multiple instances of the same component.
  </blockquote>

  <ul>
    <li>Strings can be unique</li>
    <li>Object equality not value equality</li>
  </ul>

  <pre>
    &#123;&#125; !== &#123;&#125;
  </pre>

  <ul class="notes">
    <li>Uniqueness needs to extend outside your control</li>
    <li>Javascript (thus Svelte) uses object equalitu</li>
    <li>Object equality only cares if something is the exact same instance</li>
    <li>Two empty objects defined seperately are not equal</li>
    <li>Use an empty object as your key, it's always unique!</li>
  </ul>
</div>
