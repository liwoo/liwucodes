<script>
  export let innerWidth = 900;
  export let lightMode = false;

  $: transform = `scale(${
    (100 / innerWidth) * 10 < 1 ? 1 : (100 / innerWidth) * 10
  })`;

  $: gradientColorsHorizon = [
    {
      color: lightMode ? "#7a513f" : "#7a513f",
      offset: ".0",
      stopOpacity: ".8",
    },
    {
      color: lightMode ? "#7d533f" : "#7d4f40",
      offset: ".08",
      stopOpacity: ".81",
    },
    {
      color: lightMode ? "#865a3f" : "#854942",
      offset: ".15",
      stopOpacity: ".82",
    },
    {
      color: lightMode ? "#95653e" : "#934047",
      offset: ".21",
      stopOpacity: ".86",
    },
    {
      color: lightMode ? "#ab753d" : "#a7324d",
      offset: ".27",
      stopOpacity: ".9",
    },
    {
      color: lightMode ? "#c6893d" : "#c02154",
      offset: ".33",
      stopOpacity: ".96",
    },
    {
      color: lightMode ? "#e8a23c" : "#c91b57",
      offset: ".34",
      stopOpacity: ".98",
    },
    {
      color: lightMode ? "#e8a23c" : "#c91b57",
      offset: ".34",
      stopOpacity: ".98",
    },
    {
      color: lightMode ? "#fbb03b" : "#5e0d29",
      offset: ".7",
      stopOpacity: ".45",
    },
    {
      color: lightMode ? "#fbb03b" : "#5e0d29",
      offset: "1",
      stopOpacity: "0",
    },
  ];

  $: rightSmallGradient = [
    {
      color: lightMode ? "#fbb03b" : "#ed1e79",
      offset: ".36",
      stopOpacity: "0",
    },
    {
      color: lightMode ? "#f6ad3a" : "#e81e76",
      offset: ".43",
      stopOpacity: ".98",
    },
    {
      color: lightMode ? "#e8a337" : "#db1c6f",
      offset: ".51",
      stopOpacity: ".92",
    },
    {
      color: lightMode ? "#d29231" : "#c41a63",
      offset: ".6",
      stopOpacity: ".81",
    },
    {
      color: lightMode ? "#b27b29" : "#a41752",
      offset: ".69",
      stopOpacity: ".67",
    },
    {
      color: lightMode ? "#895e20" : "#7b133c",
      offset: ".79",
      stopOpacity: ".48",
    },
    {
      color: lightMode ? "#1d1006" : "#4a0e21",
      offset: ".9",
      stopOpacity: ".26",
    },
    {
      color: lightMode ? "#110803" : "#110803",
      offset: "1",
      stopOpacity: "0",
    },
    
  ];

  $: leftLargeGradient = [
    {
      color: lightMode ? "#110803" : "#110803",
      offset: "0",
      stopOpacity: "0",
    },
    {
      color: lightMode ? "#201307" : "#140804",
      offset: "0",
      stopOpacity: ".01",
    },
    {
      color: lightMode ? "#4d3311" : "#410d1d",
      offset: ".08",
      stopOpacity: ".22",
    },
    {
      color: lightMode ? "#77511b" : "#691132",
      offset: ".15",
      stopOpacity: ".4",
    },
    {
      color: lightMode ? "#9a6b24" : "#8d1445",
      offset: ".23",
      stopOpacity: ".56",
    },
    {
      color: lightMode ? "#b8802b" : "#ab1755",
      offset: ".32",
      stopOpacity: ".7",
    },
    {
      color: lightMode ? "#d19231" : "#c31a62",
      offset: ".41",
      stopOpacity: ".81",
    },
    {
      color: lightMode ? "#e49f35" : "#d61c6d",
      offset: ".51",
      stopOpacity: ".81",
    },
    {
      color: lightMode ? "#f1a939" : "#e31d74",
      offset: ".63",
      stopOpacity: ".95",
    },
    {
      color: lightMode ? "#f9ae3a" : "#eb1e78",
      offset: ".77",
      stopOpacity: ".99",
    },
    {
      color: lightMode ? "#fbb03b" : "#ed1e79",
      offset: "1",
      stopOpacity: "1",
    },
  ];

  $: leftSlopeGradient = [
    {
      color: lightMode ? "#fbb03b" : "#ed1e79",
      offset: ".37",
      stopOpacity: "1",
    },
    {
      color: lightMode ? "#f6ad3a" : "#e81e76",
      offset: ".44",
      stopOpacity: ".98",
    },
    {
      color: lightMode ? "#e8a337" : "#db1c6f",
      offset: ".52",
      stopOpacity: ".92",
    },
    {
      color: lightMode ? "#d29231" : "#c41a63",
      offset: ".61",
      stopOpacity: ".81",
    },
    {
      color: lightMode ? "#b27b29" : "#a41752",
      offset: ".7",
      stopOpacity: ".67",
    },
    {
      color: lightMode ? "#895e20" : "#7b133c",
      offset: ".8",
      stopOpacity: ".48",
    },
    {
      color: lightMode ? "#573a14" : "#4a0e21",
      offset: ".9",
      stopOpacity: ".26",
    },
    {
      color: lightMode ? "#110803" : "#110803",
      offset: "1",
      stopOpacity: "0",
    }
  ];

  $: rightMediumGradient = [
    {
      color: lightMode ? "#fbb03b" : "#ed1e79",
      offset: ".52",
      stopOpacity: "1",
    },
    {
      color: lightMode ? "#f6ad3a" : "#e81e76",
      offset: ".57",
      stopOpacity: ".98",
    },
    {
      color: lightMode ? "#e8a337" : "#db1c6f",
      offset: ".63",
      stopOpacity: ".92",
    },
    {
      color: lightMode ? "#d29231" : "#c41a63",
      offset: ".7",
      stopOpacity: ".81",
    },
    {
      color: lightMode ? "#b27b29" : "#a41752",
      offset: ".77",
      stopOpacity: ".67",
    },
    {
      color: lightMode ? "#895e20" : "#7b133c",
      offset: ".85",
      stopOpacity: ".48",
    },
    {
      color: lightMode ? "#573a14" : "#4a0e21",
      offset: ".92",
      stopOpacity: ".26",
    },
    {
      color: lightMode ? "#110803" : "#110803",
      offset: "1",
      stopOpacity: "0",
    }
  ];

  $: leftMediumGradient = [
    {
      color: lightMode ? "#fbb03b" : "#ed1e79",
      offset: lightMode ? ".37" : ".52",
      stopOpacity: "1",
    },
    {
      color: lightMode ? "#f6ad3a" : "#e81e76",
      offset: lightMode ? ".43" : ".57",
      stopOpacity: ".98",
    },
    {
      color: lightMode ? "#e8a337" : "#db1c6f",
      offset: lightMode ? ".51" : ".63",
      stopOpacity: ".92",
    },
    {
      color: lightMode ? "#d29231" : "#c41a63",
      offset: lightMode ? ".6" : ".7",
      stopOpacity: ".81",
    },
    {
      color: lightMode ? "#b27b29" : "#a41752",
      offset: lightMode ? ".69" : ".77",
      stopOpacity: ".67",
    },
    {
      color: lightMode ? "#895e20" : "#7b133c",
      offset: lightMode ? ".78" : ".85",
      stopOpacity: ".48",
    },
    {
      color: lightMode ? "#573a14" : "#4a0e21",
      offset: lightMode ? ".8" : ".92",
      stopOpacity: ".26",
    },
    {
      color: lightMode ? "#110803" : "#110803",
      offset: "1",
      stopOpacity: "0",
    }
  ];
</script>

<style lang="scss">
  $transform: var(--transform);

  div {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 100px;
    transform: $transform;
    .street {
      margin-left: -5%;
      width: 105%;
    }
  }
</style>

<div style="--transform:{transform}">
  <svg
    xmlns="http://www.w3.org/2000/svg"
    viewBox="0 320 2150 700"
    class="street">
    <defs>
      <linearGradient
        id="build-linear-gradient"
        x1="1121.17"
        y1="517.5"
        x2="1121.17"
        y2="156.11"
        gradientUnits="userSpaceOnUse">
        {#each gradientColorsHorizon as color}
          <stop offset="{color.offset}" stop-color="{color.color}" stop-opacity="{color.stopOpacity}" />
        {/each}
      </linearGradient>
      <linearGradient
        id="build-linear-gradient-2"
        x1="267.68"
        y1="646.83"
        x2="409.68"
        y2="646.83"
        gradientUnits="userSpaceOnUse">
        {#each leftLargeGradient as color}
          <stop offset="{color.offset}" stop-color="{color.color}" stop-opacity="{color.stopOpacity}" />
        {/each}
      </linearGradient>
      <linearGradient
        id="build-linear-gradient-3"
        x1="1649.68"
        y1="787.33"
        x2="1751.68"
        y2="787.33"
        gradientUnits="userSpaceOnUse">
        {#each rightSmallGradient as color}
          <stop offset="{color.offset}" stop-color="{color.color}" stop-opacity="{color.stopOpacity}" />
        {/each}
      </linearGradient>
      <linearGradient
        id="build-linear-gradient-4"
        x1="650.68"
        y1="754.33"
        x2="762.68"
        y2="754.33"
        gradientUnits="userSpaceOnUse">
       {#each leftMediumGradient as color}
          <stop offset="{color.offset}" stop-color="{color.color}" stop-opacity="{color.stopOpacity}" />
        {/each} 
      </linearGradient>
      <linearGradient
        id="build-linear-gradient-5"
        x1="1050.68"
        y1="722.83"
        x2="988.68"
        y2="722.83"
        gradientUnits="userSpaceOnUse">
        {#each leftSlopeGradient as color}
          <stop offset="{color.offset}" stop-color="{color.color}" stop-opacity="{color.stopOpacity}" />
        {/each}
      </linearGradient>
      <linearGradient
        id="build-linear-gradient-6"
        x1="1354.68"
        y1="765.33"
        x2="1437.68"
        y2="765.33"
        gradientUnits="userSpaceOnUse">
       {#each rightMediumGradient as color}
          <stop offset="{color.offset}" stop-color="{color.color}" stop-opacity="{color.stopOpacity}" />
        {/each} 
      </linearGradient>
      <linearGradient
        id="build-linear-gradient-dark"
        x1="1147.19"
        y1="1118.27"
        x2="1147.19"
        gradientUnits="userSpaceOnUse">
        <stop offset="0" stop-color="#110803" stop-opacity="0" />
        <stop offset=".14" stop-color="#0b0502" stop-opacity=".37" />
        <stop offset="1" />
      </linearGradient>
      <clipPath id="clip-path" transform="translate(-2.74 409.16)">
        <path
          fill="none"
          d="M2164 553.06V280.73h-413l-41 11.65v-54.65h-273l-31
          19.42v-85.42h-273v147.96h-9.01v25.94h-16.87v-59.68h-28.54v121.82h-5.19v-69.92H1050v-86.12l-62-101H697.18v-17.86l-38.41-22.54.54
          107.22-9.31-3.82H409v-140l-142-72v-.5H0v473.5h102.77v138.01H2164v-59.68z" />
      </clipPath>
      <style>
        .cls-16 {
          fill: none;
        }
        .cls-2 {
          fill: #110803;
        }
        .cls-5 {
          fill: #bc998a;
        }
        .cls-16,
        .cls-5,
        .cls-6 {
          stroke: #000;
          stroke-linecap: round;
          stroke-linejoin: round;
          stroke-width: 1.35px;
        }
        .cls-6 {
          fill: #936351;
        }
        .cls-15 {
          fill: #5b3f31;
        }
        .cls-17 {
          fill: #fff;
          opacity: 0.06;
        }
        .cls-19 {
          opacity: 0.29;
        }
      </style>
    </defs>
    <g id="Layer_2" data-name="Layer 2">
      <g id="Midground">
        <path class="cls-2" d="M1094.83 754.24h51.89v83.03h-51.89z" />
        <path
          class="cls-2"
          d="M1124.66 728.29h44.11v124.54h-44.11zM1042.93
          746.46h31.14v101.19h-31.14zM1079.26 694.56h28.54v140.11h-28.54z" />
        <path fill="#af7558" d="M103.45 816.37h2061.23v204.97H103.45z" />
        <path
          d="M165.47 166.25l1995-10.14c7.05 1.43-13 357.61-54.49
          349.68-2.41-.46-998.18 0-998.18 0h-30.44L1052 478.32l-45.66
          27.47H609.28L80.49 517.5z"
          transform="translate(-2.74 409.16)"
          fill="url(#build-linear-gradient)" />
        <path class="cls-5" d="M267.68 410.33l142 72v389l-142 12v-473z" />
        <path
          class="cls-6"
          d="M394.29 574.77l-111.57-43.1v-81l111.57 54.87v69.23zM394.46
          672.46l-111.57-43.1v-81l111.57 42.87v81.23z" />
        <path
          fill="url(#build-linear-gradient-2)"
          opacity=".55"
          stroke="#000"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.35"
          d="M267.68 410.33l142 72v389l-142 12v-473z" />
        <path
          fill="#ad998e"
          stroke="#000"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.35"
          d="M103.45 961.67h2061.23v59.68H103.45z" />
        <path
          fill="#917a70"
          stroke="#000"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.35"
          d="M103.45 991.51h2061.23v29.84H103.45z" />
        <path
          class="cls-5"
          d="M.68 409.83h267v473.5H.68zM1751.68 689.33h413v196h-413zM1751.68
          689.33l-102 29v161.29l102 5.71v-196z" />
        <path
          fill="url(#build-linear-gradient-3)"
          opacity=".55"
          stroke="#000"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.35"
          d="M1751.68 689.33l-102 29v161.29l102 5.71v-196z" />
        <path class="cls-2" d="M1157.79 765.84h224.77v120.51h-224.77z" />
        <path class="cls-5" d="M383.68 622.33h267v264h-267z" />
        <path class="cls-5" d="M650.68 622.33l112 46v200l-112 18v-264z" />
        <path
          fill="url(#build-linear-gradient-4)"
          opacity=".55"
          stroke="#000"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.35"
          d="M650.68 622.33l112 46v200l-112 18v-264z" />
        <path class="cls-5" d="M679.68 559.33h309v327h-309z" />
        <path class="cls-5" d="M988.68 559.33l62 101v198l-62 28v-327z" />
        <path
          fill="url(#build-linear-gradient-5)"
          opacity=".55"
          stroke="#000"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.35"
          d="M988.68 559.33l62 101v198l-62 28v-327z" />
        <path
          class="cls-5"
          d="M1437.68 646.33h273v238h-273zM1437.68 646.33l-83 52v166l83 20v-238z" />
        <path
          fill="url(#build-linear-gradient-6)"
          opacity=".55"
          stroke="#000"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.35"
          d="M1437.68 646.33l-83 52v166l83 20v-238z" />
        <path class="cls-5" d="M1133.68 580.33h273v306h-273z" />
        <path
          fill="#ededed"
          stroke="#000"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.35"
          d="M697.85 733.33l-37.35-6.57-1.05-207.82 38.4 22.54v191.85z" />
        <path
          class="cls-6"
          d="M1157.79 631.07h61.76v73.64h-61.76zM1239.3
          631.07h61.76v73.64h-61.76zM1320.81 631.07h61.76v73.64h-61.76zM1461.79
          677.53h61.76v73.64h-61.76zM1543.3 677.53h61.76v73.64h-61.76zM1624.81
          677.53h61.76v73.64h-61.76zM1461.79 776.2h61.76v73.64h-61.76zM1624.81
          776.2h61.76v73.64h-61.76zM719.87 631.06h61.76v73.64h-61.76zM801.38
          631.07h61.76v73.64h-61.76zM882.88 631.07h61.76v73.64h-61.76z" />
        <path
          class="cls-15"
          d="M1782.23 751.17h105.08v135.17h-105.08zM1920.91
          751.17h105.08v135.17h-105.08zM2059.6
          751.17h105.08v135.17H2059.6zM1157.79
          765.84h224.77v120.51h-224.77zM1543.3 776.2h61.76v109.13h-61.76zM719.87
          765.84h224.77v120.51H719.87z" />
        <path
          class="cls-16"
          d="M1103.91 960.89l-11.68 30.62v29.84M1345.2 961.67l40.22
          29.84v30.87M1591.58 961.67l86.21 29.84v29.84M1878.91 961.67l172.21
          29.84v29.84M845.75 960.89l-60.98 30.23v30.23M103.45 985.16h2061.23" />
        <path
          class="cls-17"
          d="M781.63 635.77v25.6l-33.18 30.6-11.68 7.78-2.59-7.14-13.3
          12.09-1.01-23.05 14.96-13.04 3.24 7.14 43.56-39.98zM863.36
          635.77v25.6l-33.18 30.6-11.68 7.78-2.59-7.14-13.3 12.09-1.01-23.05
          14.96-13.04 3.24 7.14 43.56-39.98zM943.79 635.77v25.6l-33.18
          30.6-11.68 7.78-2.59-7.14-13.3 12.09-1.01-23.05 14.96-13.04 3.24 7.14
          43.56-39.98zM1220.11 635.77v25.6l-33.18 30.6-11.68 7.78-2.59-7.14-13.3
          12.09-1.01-23.05 14.96-13.04 3.24 7.14 43.56-39.98zM1300.55
          635.77v25.6l-33.18 30.6-11.68 7.78-2.59-7.14-13.3 12.09-1.01-23.05
          14.96-13.04 3.24 7.14 43.56-39.98zM1382.28 635.77v25.6l-33.18
          30.6-11.68 7.78-2.59-7.14-13.3 12.09-1.01-23.05 14.96-13.04 3.24 7.14
          43.56-39.98zM1523.98 680.53v25.6l-33.18 30.6-11.68 7.78-2.59-7.14-13.3
          12.09-1.01-23.05 14.96-13.04 3.24 7.14 43.56-39.98zM1523.98
          779.77v25.6l-33.18 30.6-11.68 7.78-2.59-7.14-13.3 12.09-1.01-23.05
          14.96-13.04 3.24 7.14 43.56-39.98zM1604.41 680.53v25.6l-33.18
          30.6-11.68 7.78-2.59-7.14-13.3 12.09-1.01-23.05 14.96-13.04 3.24 7.14
          43.56-39.98zM1686.14 680.53v25.6l-33.18 30.6-11.68 7.78-2.59-7.14-13.3
          12.09-1.01-23.05 14.96-13.04 3.24 7.14 43.56-39.98zM1686.79
          779.13v25.6l-33.18 30.6-11.68 7.78-2.59-7.14-13.3 12.09-1.01-23.05
          14.96-13.04 3.24 7.14 43.56-39.98z" />
        <path
          d="M663 242.6s7.65-25.94 18.42-25.62S700 190.06 700 190.06l.64
          134.12-37.35-6.57z"
          transform="translate(-2.74 409.16)"
          fill="#95dd57" />
        <path
          class="cls-19"
          d="M690.5 565.27l-23.78-11.68v-11.24l23.78 11.67v11.25zM693.53
          585.59l-26.81-10.81v-11.24l26.81 10.81v11.24zM694.18
          719.43l-27.46-8v-11.24l27.46 8v11.24z" />
        <g clip-path="url(#clip-path)">
          <path
            opacity="{lightMode ? `0` : `.65`}"
            fill="url(#build-linear-gradient-dark)"
            d="M100.27 0h2093.84v1118.27H100.27z" />
        </g>
      </g>
    </g>
  </svg>
</div>
