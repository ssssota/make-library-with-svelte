<script lang="ts">
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher<{
    leftclick: void;
    rightclick: void;
  }>();
  export let enableLeft = true;
  export let enableRight = true;
  const onLeftClick = () => dispatch("leftclick");
  const onRightClick = () => dispatch("rightclick");
</script>

<div class="wrapper">
  <section class="slide">
    <slot />
  </section>
  {#if enableLeft}
    <button class="left cursor" on:click={onLeftClick} />
  {/if}
  {#if enableRight}
    <button class="right cursor" on:click={onRightClick} />
  {/if}
</div>

<style>
  .wrapper {
    background-color: black;
    width: 100%;
    height: 100%;

    padding: 0;
    margin: 0;

    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  button {
    background-color: transparent;
    border: none;
    outline: none;
  }

  .left {
    position: absolute;
    width: 50%;
    height: 100%;
    left: 0;
    top: 0;
  }
  .left.cursor {
    cursor:
      url(../images/left.svg) 0 0,
      pointer;
  }
  .right {
    position: absolute;
    width: 50%;
    height: 100%;
    right: 0;
    top: 0;
  }
  .right.cursor {
    cursor:
      url(../images/right.svg) 0 0,
      pointer;
  }
  :root {
    --slide-width: min(100vw, calc(400vh / 3));
    --slide-height: min(75vw, 100vh);
    --base-font-size: calc(var(--slide-width) / 40);
  }

  .slide {
    background-color: var(--background-color, white);

    width: var(--slide-width);
    height: var(--slide-height);
  }
  .slide :global(h1) {
    font-size: calc(var(--base-font-size) * 2);
  }
  .slide :global(h2) {
    font-size: calc(var(--base-font-size) * 1.6);
  }
  .slide :global(h3) {
    font-size: calc(var(--base-font-size) * 1.4);
  }
  .slide :global(h4),
  .slide :global(h5),
  .slide :global(h6),
  .slide :global(p),
  .slide :global(li),
  .slide :global(dl),
  .slide :global(table),
  .slide :global(blockquote),
  .slide :global(pre) {
    font-size: calc(var(--base-font-size) * 1.2);
  }
  .slide :global(small) {
    font-size: calc(var(--base-font-size) * 0.8);
  }
  .slide :global(li p) {
    margin: 0;
  }
  .slide :global(pre) {
    background-color: #f0f0f0;
    padding: 0.5em;
    border-radius: 0.5em;
  }
  .slide :global(code) {
    color: #5d3ee8;
  }
</style>
