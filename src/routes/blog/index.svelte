<script context="module">
  export function preload({ params, query }) {
    return this.fetch(`blog.json`)
      .then((r) => r.json())
      .then((posts) => {
        return { posts };
      });
  }
</script>

<script>
  import { onMount, afterUpdate } from "svelte";

  import Thumbnail from "../../components/blog/Thumbnail.svelte";
  import Container from "../../components/Container.svelte";
  import Header from "../../components/Header.svelte";
  import LargeButton from "../../components/LargeButton.svelte";
  import Spacer from "../../components/Spacer.svelte";
  import { lightMode } from "../../store";
  import { fly, fade } from "svelte/transition";
  import WindowView from "../../components/blog/WindowView.svelte";
  export let posts;

  let innerHeight;
  let innerWidth;

  let startAnimation = false;

  function resetBackground() {
    if ($lightMode === true) window.document.body.classList = "blog-light";
    if ($lightMode === false) window.document.body.classList = "blog-dark";
  }

  onMount(() => {
    resetBackground();

    setTimeout(() => {
      startAnimation = true;
    }, 2000);
  });

  afterUpdate(() => {
    resetBackground();
  });
</script>

<svelte:head>
  <title>Blog</title>
</svelte:head>
<svelte:window bind:innerHeight bind:innerWidth />
<Header lightMode={$lightMode}>
  <header
    class="tw-w-full tw-pt-32 tw-pb-16 tw-flex tw-flex-col xl:tw-flex-row tw-items-stretch"
  >
    <WindowView lightMode={$lightMode} />
    <!-- content here -->
    <div
      class="tw-w-full xl:tw-w-4/5 xl:tw-pl-8 tw-mt-4 tw-flex tw-text-center xl:tw-text-left tw-flex-col tw-justify-start"
    >
      {#if startAnimation}
        <h2
          in:fly={{ y: -30 }}
          class="{$lightMode
            ? `tw-text-black`
            : `tw-text-yellow-500`} tw-text-xl sm:tw-text-3xl md:tw-text-4xl xl:tw-text-5xl ul:tw-text-6xl tw-font-extrabold"
        >
          My thoughts on Tech, Code and Life!
        </h2>
        <h3
          in:fly={{ y: -30 }}
          class="tw-text-sm tw-font-normal tw-mb-8 tw-text-gray-600"
        >
          Signup to my mailing list and get notified as soon as I have something
          new to say
        </h3>
        <input
          in:fly={{ y: -30 }}
          class="tw-bg-gray-{$lightMode
            ? `100`
            : `900`} tw-rounded-full tw-text-gray-{$lightMode
            ? `900`
            : `100`}  tw-border-black tw-border tw-text-lg tw-p-4 md:tw-w-2/3 md:tw-m-auto xl:tw-m-0"
          type="text"
          placeholder="Enter your Email Address here"
        />
        <div in:fly={{ y: 20, delay: 500 }} class="tw-w-18">
          <LargeButton lightMode={$lightMode}
            >Signup to Mailing List</LargeButton
          >
        </div>
      {/if}
    </div>
  </header>
</Header>
<Container>
  {#if startAnimation}
    <div
      in:fade={{ delay: 1000 }}
      class="tw-bg-gray-200 tw-w-full tw-my-8 tw-flex tw-sticky top-0"
    >
      <ul
        class="tw-list-none tw-inline-flex tw-w-3/4 tw-justify-around tw-text-gray-600  tw-border-gray-600 tw-border-solid tw-border-l-0 tw-border-t-0 tw-border-b-0 tw-border-r"
      >
        <li class="tw-text-gray-800 tw-font-bold">Opinions</li>
        <li>Technical</li>
        <li>Videos</li>
        <li>Life</li>
      </ul>
      <!-- secondary nav -->
      <div class="tw-flex tw-w-full tw-align-middle tw-pl-4">
        <svg
          class="tw-w-6 tw-h-auto"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 25 26"
        >
          <g stroke="#979797" fill="none" fill-rule="evenodd">
            <circle stroke-width="3" cx="8.5" cy="8.5" r="7" />
            <path
              stroke-width="4"
              stroke-linecap="round"
              d="M14.321 15.321l8.358 8.358"
            />
          </g>
        </svg>
        <input
          class="tw-w-full tw-text-lg tw-bg-transparent tw-border-none tw-py-2 tw-px-4"
          type="text"
          placeholder=""
        />
      </div>
    </div>
  {/if}
  {#if startAnimation}
    <div
      in:fly={{ y: 50, delay: 2000 }}
      class="tw-grid-cols-1 xl:tw-grid-cols-2 tw-grid tw-gap-4"
    >
      {#each posts as post}
        <Thumbnail
          lightMode={$lightMode}
          title={post.title}
          slug={post.slug}
          image="https://res.cloudinary.com/tiyeni/image/upload/v1606097900/faith_mussa.jpg"
          imageAlt="Faith Mussa"
          category="Opinion"
          excerpt="With so many languages and frameworks to master as a Software Developer, it can be overwhelming to choose where to start from."
        />
      {/each}
    </div>
  {/if}
  <Spacer />
</Container>

<style>
  :global(body.blog-dark) {
    transition: all 0.3s;
    background: #292941;
  }
  :global(body.blog-light) {
    transition: all 0.3s;
    background: #c6e7ef;
  }
</style>
