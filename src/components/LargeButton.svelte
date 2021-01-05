<script>
    export let twBgColor = "yellow-500";
    export let twTextColor = "blue-500";
</script>

<button class="tw-my-2 tw-border-none tw-text-lg md:tw-text-xl tw-text-{twTextColor} tw-px-8 md:tw-px-12 tw-py-4 tw-rounded-full tw-uppercase tw-cursor-pointer tw-font-medium tw-bg-{twBgColor} tw-mr-4">
    <slot />
</button>