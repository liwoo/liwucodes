<script>
  import Nav from "../components/Nav.svelte";
  // import Tailwind from "../components/Tailwind.svelte";

  export let segment;
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }
  
</style>

<!-- <Tailwind /> -->
<Nav {segment} />

<main>
  <slot />
</main>
