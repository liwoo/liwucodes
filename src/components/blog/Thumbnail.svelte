<script>
  export let lightMode;
  export let title = "Sample Title";
  export let category = "Marketing";
  export let excerpt = "Some Leading text to fill up the space.";
  export let date = "14 January 2021";
  export let slug = "some-sample-slug";
  export let image =
    "https://res.cloudinary.com/tiyeni/image/upload/v1606097900/faith_mussa.jpg";
  export let imageAlt = "Faith Mussa";
</script>

<article
  class="tw-rounded-lg tw-bg-gray-{lightMode
    ? `200`
    : `900`} tw-shadow-sm tw-text-{lightMode ? `black` : `white`}"
>
  <img
    class="tw-mb-4 tw-w-full tw-h-64 tw-object-cover tw-rounded-tl-lg tw-rounded-tr-lg"
    src={image}
    alt={imageAlt}
  />
  <div class="tw-mx-8">
    <div class="tw-w-full tw-flex tw-justify-between">
      <caption
        class="tw-bg-purple-300 tw-px-2 tw-rounded tw-text-purple-800 tw-font-semibold tw-uppercase tw-text-sm"
        >{category}</caption
      >
      <caption class="tw-text-gray-600">{date}</caption>
    </div>
    <h3 class="tw-my-4"><a rel="prefetch" href="blog/{slug}">{title}</a></h3>
    <p>{excerpt}</p>
  </div>
</article>
