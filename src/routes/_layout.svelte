<script>
  import Nav from "../components/Nav.svelte";
  import { lightMode } from "../store";
  // import Tailwind from "../components/Tailwind.svelte";

  export let segment;
</script>

<!-- <Tailwind /> -->
<Nav {segment} />

<main>
  <slot />
</main>

<style>
  * {
    margin: 0;
    padding: 0;
  }
</style>
