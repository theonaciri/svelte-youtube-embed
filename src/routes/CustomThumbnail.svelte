<script>
  import Youtube from "$lib/Youtube.svelte";
  import Prism from "./Prism.svelte";
</script>

<h2>Custom thumbnail</h2>
<p>
  Similar to how we can use custom play button, we can also use custom
  thumbnails.
</p>
<p>
  Use <strong>thumbnail</strong> snippet to add image/picture html tag inside
  <em>Yoututbe</em> component.
</p>

<Youtube id="EBtsu6naB8g">
  {#snippet thumbnail()}
    <img
      slot="thumbnail"
      src="https://picsum.photos/id/74/4288/2848"
      alt="A video on svelte"
      style="width: 100%; height: 100%; object-fit: cover; object-position: center; background: red"
    />
  {/snippet}
</Youtube>

<Prism
  code={`<Youtube id="EBtsu6naB8g">
  {#snippet thumbnail()}
    <img
      slot="thumbnail"
      alt="A video on svelte"
      src="/path/image.jpg"
      style="width: 100%; height: 100%; object-fit: contain; object-position: center; background: red"
    />
  {/snippet}
  <!-- inline styles are optional -->
</Youtube>
`}
/>
