<script>
  export let width = "900px";
  export let height = "400px";
</script>

<style lang="scss">
  $width: var(--width);
  $height: var(--height);
  div {
    position: absolute;
    width: $width;
    height: $height;
    overflow: hidden;
  }
</style>

<div style="--width:{width}; --height:{height}">
  <slot>
    <!-- optional fallback -->
  </slot>
</div>
