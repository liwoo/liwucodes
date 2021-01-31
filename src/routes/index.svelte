<script>
  import MainBackground from "../components/index/MainBackground.svelte";
  import Stars from "../components/index/Stars.svelte";
  import Clouds from "../components/index/Clouds.svelte";
  import Street from "../components/index/Street.svelte";
  import Car from "../components/index/Car.svelte";
  import MeAndPole from "../components/index/PoleAndMe.svelte";
  import Container from "../components/Container.svelte";
  import LargeButton from "../components/LargeButton.svelte";
  import { onMount } from "svelte";
  import { derived } from "svelte/store";
  import { lightMode } from "../store.js";
  import { fade } from "svelte/transition";

  let innerHeight;
  let innerWidth;

  // initialize background

  $: height = `${innerHeight}px`;
  $: width = `${innerWidth}px`;
  $: cloudAltPosition = -innerWidth;

  // change background depending on lightMode
  $: {
    if ($lightMode === true && skyTransitionStart === false)
      window.document.body.classList = "lightInit";
    if ($lightMode === false && skyTransitionStart === false)
      window.document.body.classList = "darkInit";
    if ($lightMode === true && skyTransitionStart === true)
      window.document.body.classList = "light";
    if ($lightMode === false && skyTransitionStart === true)
      window.document.body.classList = "";
  }

  const cloudVelocity = 0.2;
  const lightOnThreshold = 80;
  let cloudPosition = 0;
  let lightOnCounter = 0;

  let streetTransitionStart = false;
  let skyTransitionStart = false;
  let roadTranslateY = "107px";
  let poleTransitionStart = false;
  let contentTransitionStart = false;
  let carTransitionStart = false;

  let frame;
  let poleLightOn = false;
  onMount(() => {
    setTimeout(() => {
      streetTransitionStart = true;
      roadTranslateY = "0px";
    }, 200);

    setTimeout(() => {
      skyTransitionStart = true;
    }, 450);

    setTimeout(() => {
      poleTransitionStart = true;
    }, 700);

    setTimeout(() => {
      carTransitionStart = true;
    }, 1000);

    setTimeout(() => {
      contentTransitionStart = true;
    }, 1500);

    (function loop() {
      frame = requestAnimationFrame(loop);
      if (lightOnCounter === lightOnThreshold) {
        poleLightOn = !poleLightOn;
        lightOnCounter = 0;
      } else {
        lightOnCounter += 1;
      }

      if (cloudPosition > innerWidth) cloudPosition = -innerWidth;
      else {
        cloudPosition += cloudVelocity;
      }
      if (cloudAltPosition > innerWidth) cloudAltPosition = -innerWidth;
      else {
        cloudAltPosition += cloudVelocity;
      }
    })();
  });
</script>

<svelte:head>
  <title>Hi, I'm Jeremiah!</title>
</svelte:head>
<svelte:window bind:innerHeight bind:innerWidth />

<MainBackground {width} {height}>
  {#if $lightMode == false}
    <Stars {innerWidth} />
  {/if}
  {#if skyTransitionStart}
    <div in:fade>
      <Clouds
        {innerWidth}
        {cloudPosition}
        {cloudAltPosition}
        lightMode={$lightMode}
      />
    </div>
  {/if}
  <Street {innerWidth} lightMode={$lightMode} {streetTransitionStart} />
  <div id="road" style="--translateY:{roadTranslateY};" />
  <Car {innerWidth} lightMode={$lightMode} {carTransitionStart} />

  {#if contentTransitionStart}
    <div in:fade id="overlay" class:light={$lightMode === true} />
  {/if}

  <MeAndPole
    poleLightOn={$lightMode ? false : poleLightOn}
    {poleTransitionStart}
  />
</MainBackground>

<Container>
  <div
    style="height: {height}; z-index: 999;"
    class="tw-flex tw-flex-col tw-justify-center"
  >
    {#if contentTransitionStart}
      <h1
        in:fade
        class="{$lightMode
          ? `tw-text-black`
          : `tw-text-white`} tw-text-2xl tw-my-6"
      >
        Hi, I'm Jeremiah Chienda
      </h1>
      <h2
        in:fade
        class="tw-text-2xl md:tw-text-4xl {$lightMode
          ? `tw-text-black`
          : `tw-text-yellow-500`} tw-uppercase
         tw-leading-relaxed"
      >
        <strong class:dark={$lightMode === false}>I am Pretty Good</strong>
        @Crafting
        <br />
        Web and Mobile Experiences
      </h2>
      <p
        in:fade
        class="{$lightMode ? `tw-text-black` : `tw-text-white`} {$lightMode
          ? `tw-bg-blue-300`
          : `tw-bg-black`} tw-p-4 tw-text-xl tw-hidden xl:tw-block"
      >
        Seriously, I am! I hold a Masters of Engineering Degree in Information
        Computer Science from
        <a href="https://www.doshisha.ac.jp/en/" target="_blank">
          Doshisha University
        </a>
        and more than 4 years of Professional Experience building Software for
        <a href="http://baobabhealth.org">Health</a>
        ,
        <a href="https://oneacrefund.org">Agriculture</a>
        and
        <a href="https://nbs.mw">Finance</a>
        in Malawi and Rwanda.
      </p>
      <div
        in:fade={{ delay: 800 }}
        class="tw-flex tw-mt-2 tw-flex-col lg:tw-flex-row"
      >
        <LargeButton
          twBgColor={$lightMode ? `blue-500` : `yellow-500`}
          twTextColor={$lightMode ? `yellow-500` : `blue-500`}
        >
          Get in Touch
        </LargeButton>
        <LargeButton
          twBgColor={$lightMode ? `yellow-500` : `blue-500`}
          twTextColor={$lightMode ? `blue-500 ` : `yellow-500`}
        >
          View my Work
        </LargeButton>
      </div>
    {/if}
  </div>
</Container>

<style lang="scss">
  $bg: linear-gradient(
    180deg,
    rgba(27, 20, 100, 1) 0%,
    rgba(9, 9, 121, 1) 56%,
    rgba(212, 20, 90, 1) 100%
  );

  $bgLight: linear-gradient(
    180deg,
    rgba(41, 171, 226, 1) 0%,
    rgba(218, 227, 64, 1) 88%,
    rgba(240, 234, 44, 1) 100%
  );
  :global(body) {
    transition: all 0.5s;
    height: 100%;
    background: $bg;
    background-color: #000;
    background-repeat: no-repeat;
  }

  :global(body.light) {
    background: $bgLight;
  }

  :global(body.darkInit) {
    background: #000;
  }

  :global(body.lightInit) {
    background: rgba(41, 171, 226, 1) 0%;
  }

  div {
    strong {
      background: linear-gradient(
        180deg,
        rgba(255, 255, 255, 0) 0%,
        rgba(255, 255, 255, 0) 48%,
        rgba(144, 205, 244, 1) 49%,
        rgba(144, 205, 244, 1) 100%
      );
    }
    strong.dark {
      background: linear-gradient(
        180deg,
        rgba(255, 255, 255, 0) 0%,
        rgba(255, 255, 255, 0) 50%,
        rgba(51, 102, 154, 1) 51%,
        rgba(51, 102, 154, 1) 100%
      );
    }
    > #road {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      transform: translateY(var(--translateY));
      transition: all 0.5s;
      height: 107px;
      background-color: #110803;
      z-index: -10;
    }
    > #overlay {
      position: absolute;
      background-color: rgba($color: #000000, $alpha: 0.5);
      width: 100%;
      height: 110%;
      top: -10%;
    }
    > #overlay.light {
      background-color: rgba($color: #ffc5b6, $alpha: 0.3);
    }
  }
</style>
