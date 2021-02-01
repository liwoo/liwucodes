<script>
  export let lightMode;
  export let alternative = false;
  $: twBgColor = function () {
    if (lightMode === true && alternative === false) return `blue-500`;
    if (lightMode === true && alternative === true) return `yellow-500`;
    if (lightMode === false && alternative === false) return `yellow-500`;
    if (lightMode === false && alternative === true) return `blue-500`;
  };
  $: twTextColor = function () {
    if (lightMode === true && alternative === false) return `yellow-500`;
    if (lightMode === true && alternative === true) return `blue-500`;
    if (lightMode === false && alternative === false) return `blue-500`;
    if (lightMode === false && alternative === true) return `yellow-500`;
  };
</script>

<button
  class="tw-my-2 tw-border-none tw-text-base tw-text-{twTextColor()} tw-px-8 md:tw-px-12 tw-py-4 tw-rounded-full tw-uppercase tw-cursor-pointer tw-font-bold tw-bg-{twBgColor()} tw-mr-4"
>
  <slot />
</button>
