<script>
  import Youtube from "$lib/Youtube.svelte";
  import Prism from "./Prism.svelte";

  let overlayBGColor = $state("#e5a50a");
  let overlayTransitionDuration = $state(50);
</script>

<h2>Using custom overlay</h2>
<div class="controls">
  <label for="overlay-color-select">Overlay color</label>
  <input id="overlay-color-select" type="color" bind:value={overlayBGColor} />
  <label for="overlay-transition-duration">Overlay transition duration</label>
  <div>
    <input
      id="overlay-transition-duration"
      min="0"
      max="1000"
      type="range"
      step="50"
      bind:value={overlayTransitionDuration}
    />
    <small>{overlayTransitionDuration} ms</small>
  </div>
</div>

<Youtube
  id="EBtsu6naB8g"
  --overlay-bg-color="{overlayBGColor}30"
  --overlay-transition="all {overlayTransitionDuration}ms linear"
/>

<Prism
  code={`<Youtube
  id="EBtsu6naB8g"
  --overlay-bg-color="#e5a50a30"
  --overlay-transition="all 50ms linear"
  />`}
/>

<p>
  Here the number `30` represents the opacity of `0.3`. Remove it for 100%
  opaqueness.
</p>
