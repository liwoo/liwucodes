<script>
  export let lightMode;
</script>

<section
  class="tw-bg-blue-{lightMode
    ? `300`
    : `900`} tw-pt-8 tw-px-8 md:tw-px-20 tw-relative"
>
  <slot />
</section>

<style>
  section {
    transition: all 0.3s;
  }
</style>
