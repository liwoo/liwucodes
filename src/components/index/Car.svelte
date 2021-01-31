<script>
  export let innerWidth = 900;
  export let lightMode = false;
  export let carTransitionStart;

  $: transform = `scale(${
    (100 / innerWidth) * 8 < 1 ? 1 : (100 / innerWidth) * 8
  })`;
  $: calculateLeftPosition = (endPosition) =>
    carTransitionStart ? endPosition : "-100%";
</script>

<svg
  xmlns="http://www.w3.org/2000/svg"
  viewBox="0 0 1428.44 620.28"
  style="--transform:{transform}; --first-bp-left-pos:{calculateLeftPosition(
    '-20%'
  )}; --second-bp-left-pos:{calculateLeftPosition(
    '-30%'
  )}; --third-bp-left-pos:{calculateLeftPosition(
    '-50%'
  )}; --fourth-bp-left-pos:{calculateLeftPosition('-60%')}"
>
  <defs
    ><style>
      .minib-cls-2 {
        fill: #82523c;
      }
      .minib-cls-5 {
        fill: #724738;
      }
      .minib-dark-window {
        fill: #472615;
      }
      .minib-cls-6 {
        fill: #110803;
      }
      .minib-cls-7 {
        fill: #bc998a;
        stroke: #000;
        stroke-linecap: round;
        stroke-linejoin: round;
        stroke-width: 1.35px;
      }
    </style></defs
  >
  <g id="MinibusLayer2" data-name="Layer 2">
    <g id="MinibusForeground">
      <g id="minibus">
        <path
          fill={lightMode ? `#9e7669` : `#110803`}
          d="M1426.88 541.01H0V231.38L38.92 0H1271.3l155.58 228.23v312.78z"
        />
        <path
          class={lightMode ? `minib-cls-2` : `minib-dark-window`}
          d="M1035.55 34.27h211.87l138.7
          187.99h-89.17l-28.76-39.06h-234.18l1.54-148.93zM539.54
          33.44h401.59v184.89H539.54zM59.68 218.33h428.1V33.44H82.14L59.68
          218.33z"
        />
        <path
          d="M1399.18 337.22h29.25v89.31h-42v-76.59a12.72 12.72 0 0112.75-12.72z"
          fill="#eae250"
        />
        <path
          fill={lightMode ? `#9e7669` : `#110803`}
          d="M1386.47 426.28h41.97v35h-41.97z"
        />
        <path
          class={lightMode ? `minib-cls-2` : `minib-class-6`}
          d="M1009.53 475.06l50.54-102.9h184.37l50.39
          113.39v55.46h-285.3v-65.95z"
        />
        <circle class="minib-cls-6" cx="1152.5" cy="506.82" r="113.46" />
        <path
          class="minib-cls-5"
          d="M131.08 475.06l50.54-102.9h184.37l50.39 113.39v55.46h-285.3v-65.95z"
        />
        <circle class="minib-cls-6" cx="274.05" cy="506.82" r="113.46" />
        <circle
          class={lightMode ? `minib-cls-7` : `minib-class-6`}
          cx="274.05"
          cy="506.82"
          r="63.04"
        />
        <circle
          class={lightMode ? `minib-cls-7` : `minib-class-6`}
          cx="1152.18"
          cy="506.82"
          r="63.04"
        />
      </g>
    </g>
  </g>
</svg>

<style lang="scss">
  $transform: var(--transform);
  svg {
    position: absolute;
    left: var(--first-bp-left-pos);
    transition: all 0.7s;
    bottom: 7%;
    width: 55%;
    transform: scale(1.2);

    @media all and (min-width: 687px) and (max-width: 802px) {
      bottom: 5%;
    }

    @media all and (max-width: 1600px) {
      transform: scale(1.6);
    }

    @media all and (max-width: 686px) {
      bottom: 4%;
      left: var(--second-bp-left-pos);
      transform: $transform;
    }

    @media all and (max-width: 400px) {
      left: var(--third-bp-left-pos);
    }

    @media all and (max-width: 350px) {
      left: var(--fourth-bp-left-pos);
    }

    @media all and (max-width: 300px) {
      display: none;
    }
  }
</style>
