<script lang="ts">
  import ProgressBar from "./components/ProgressBar.svelte";
  import SlideView from "./components/SlideView.svelte";
  import "./global.css";
  import Agenda from "./pages/Agenda.svelte";
  import Conclusion from "./pages/Conclusion.svelte";
  import How from "./pages/How.svelte";
  import Introduce from "./pages/Introduce.svelte";
  import Pain from "./pages/Pain.svelte";
  import Svelte5 from "./pages/Svelte5.svelte";
  import Tips from "./pages/Tips.svelte";
  import Title from "./pages/Title.svelte";
  import Why from "./pages/Why.svelte";
  import { page } from "./utils/page";
  export let listView = false;

  const pages = [
    Title,
    Introduce,
    Agenda,
    Why,
    How,
    Pain,
    Svelte5,
    Tips,
    Conclusion,
    // INSERT YOUR PAGE HERE!
  ];

  const handleKeydown = (e: KeyboardEvent) => {
    switch (e.code) {
      case "ArrowRight":
      case "Space":
      case "Enter":
        page.next();
        break;
      case "ArrowLeft":
        page.prev();
        break;
    }
  };
</script>

<svelte:window on:keydown={handleKeydown} />

{#if !listView}
  <SlideView
    on:leftclick={page.prev}
    on:rightclick={page.next}
    enableLeft
    enableRight
  >
    <svelte:component this={pages[$page - 1]} />
  </SlideView>
  <ProgressBar progress={($page - 1) / (pages.length - 1)} />
{:else}
  {#each pages as p}
    <SlideView>
      <svelte:component this={p} />
    </SlideView>
  {/each}
{/if}
