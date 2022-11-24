<script lang="ts">
  import Clickable from "./Clickable.svelte";
  import Purchasable from "./Purchasable.svelte";
</script>

<!-- This is super janky but the other options on StackOverflow sucked. -->
<div id="grid-container">
  <div id="clickable">
    <Clickable/>
  </div>
  <div id="purchasable">
    <Purchasable/>
  </div>
</div>


<style>
  #grid-container {
    display: grid; 
    grid-template-rows: 100%;
    grid-template-columns: 25% 75%;
  }
  #clickable {
    grid-row-start: 1;
    grid-column-start: 1;
    grid-row-end: 2;
    grid-column-end: 2;
    height: 100%;
    top: 50%;
    left: -25%;
    transform: translate(0, 50%);
  }
  #purchasable {
    grid-row-start: 1;
    grid-column-start: 2;
    grid-row-end: 2;
    grid-column-end: 3;
  }
</style>