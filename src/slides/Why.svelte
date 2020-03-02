<div class="slide alt2">
  <h4>Why?</h4>

  <ul>
    <li>No passing props &amp; stores down the hierarchy</li>
    <li>Top-driven state, single data flow direction</li>
    <li>Stores don't work well in .js files</li>
    <li>Stop multiple instances of a component conflicting</li>
  </ul>

  <ul class="notes">
    <li>Don't litter code with props, stores are hard to pass - dollar, no dollar</li>
    <li>Bi-directional data is harder to reason about</li>
    <li>Subscriptions don't work well - how do you unsubscribe</li>
    <li>Unique keys mean no crossover</li>
  </ul>
</div>
