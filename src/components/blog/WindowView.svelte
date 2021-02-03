<script>
  import { onMount } from "svelte";
  import { fly } from "svelte/transition";
  export let lightMode = false;
  let isBlinderClosed = true;

  $: windowColor = lightMode ? "#FDFFFF" : "#97B7BD";
  $: windowFrameColor = lightMode ? "#FFF" : "#BDDFE9";
  $: windowFrameLinesColor = lightMode ? "#B3D3DC" : "#7597A1";
  $: windowFrameLighterColor = lightMode ? "#FFF" : "#D6F8FF";

  $: outsideBgLightColor = lightMode ? "#B0FFF9" : "#5365E5";
  $: outsideBgMediumColor = lightMode ? "#A0F9F4" : "#4755C3";
  $: outsideBgDarkColor = lightMode ? "#A0F9F4" : "#3b44a09e";
  $: outsideBgColor = lightMode ? "#8FF2EF" : "#22225B";

  $: buildingLightColor = lightMode ? "#81C7E2" : "#2F2F72";
  $: buildingMediumColor = lightMode ? "#4CBBEC" : "#363684";
  $: buildingDarkColor = lightMode ? "#5BA7DD" : "#22225B";

  $: buildingLight1Color = lightMode ? "#8ED7ED" : "#FFDB56";
  $: buildingLight2Color = lightMode ? "#8ED7ED" : "#FF996C";
  $: buildingLight3Color = lightMode ? "#8ED7ED" : "#AC6F6E";
  $: buildingLight4Color = lightMode ? "#8ED7ED" : "#A76965";
  $: buildingLight5Color = lightMode ? "#8ED7ED" : "#AF7176";
  $: buildingLight6Color = lightMode ? "#8ED7ED" : "#BD7D3F";

  $: buildingLight7Color = lightMode ? "#8ED7ED" : "#3E3E8C";
  $: buildingLight8Color = lightMode ? "#8ED7ED" : "#2C2C6B";
  $: buildingLight9Color = lightMode ? "#8ED7ED" : "#3A3A84";

  onMount(() => {
    setTimeout(() => {
      isBlinderClosed = false;
    }, 500);
  });
</script>

<svg class="tw-w-full" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 720 437">
  <defs>
    <clipPath id="cloud-holder">
      <path d="M81 103h562v129H81z" />
    </clipPath>
  </defs>
  <!-- start outside background -->
  <path
    fill={windowFrameLinesColor}
    fill-rule="evenodd"
    d="M57.65 431.69h605.89V48.602H57.65V431.69z"
    clip-rule="evenodd"
  />
  <path
    fill={outsideBgColor}
    fill-rule="evenodd"
    d="M79.175 406.88h562.841V64.009H79.175V406.88z"
    clip-rule="evenodd"
  />
  <!-- start moon -->
  {#if !lightMode}
    <g class="moon">
      <circle cx="306.975" cy="180.977" r="23.975" fill="#4e3a5e70" />
      <circle
        cx="306.975"
        cy="180.977"
        r="23.975"
        fill="#714D61"
        stroke="#4E3A5E"
        stroke-width="8"
      >
        <animate
          attributeName="opacity"
          from="1"
          to="0"
          dur="3s"
          repeatCount="indefinite"
        />
        <animate
          attributeName="r"
          attributeType="XML"
          from="15.7"
          to="23.975"
          begin="0s"
          dur="3s"
          fill="remove"
          repeatCount="indefinite"
        />
      </circle>
      <path
        fill="#FFDB56"
        fill-rule="evenodd"
        d="M306.851 180.954a25.518 25.518 0 00-4.98-15.181 15.708 15.708 0 0113.587 2.744 15.704 15.704 0 016.118 12.437 15.694 15.694 0 01-12.593 15.389 15.694 15.694 0 01-7.112-.209 25.513 25.513 0 004.98-15.18"
        clip-rule="evenodd"
        class="moon"
      />
    </g>
  {/if}
  <!-- end moon -->
  <path
    class="jamming"
    fill={outsideBgDarkColor}
    fill-rule="evenodd"
    d="M79.175 418h562.841V191.438H79.175V418z"
    clip-rule="evenodd"
  />
  <path
    class="jamming"
    fill={outsideBgMediumColor}
    fill-rule="evenodd"
    d="M79.175 406.88h562.841V221.084H79.175V406.88z"
    clip-rule="evenodd"
  />
  <path
    class="jamming"
    fill={outsideBgLightColor}
    fill-rule="evenodd"
    d="M79.175 406.88h562.841V277.133H79.175V406.88z"
    clip-rule="evenodd"
  />
  <!-- end outside background -->

  {#if lightMode}
    <!-- sun -->
    <g fill-rule="evenodd" clip-rule="evenodd" class="sun">
      <circle
        cx="438.28"
        cy="148.19"
        r="36.41"
        fill="#FFE160"
        stroke="#FBEC5D"
        stroke-width="10"
      >
        <animate
          attributeName="opacity"
          from="1"
          to="0"
          dur="3s"
          repeatCount="indefinite"
        />
        <animate
          attributeName="r"
          attributeType="XML"
          from="19"
          to="36.41"
          begin="0s"
          dur="3s"
          fill="remove"
          repeatCount="indefinite"
        />
      </circle>
      <circle cx="438" cy="148" r="20" fill="#FFE160" />
    </g>
    <!-- start clouds-l -->
    <g
      fill="#B0FFF9"
      fill-rule="evenodd"
      clip-rule="evenodd"
      class="tw-overflow-hidden"
      clip-path="url(#cloud-holder)"
    >
      <path
        fill-rule="evenodd"
        d="M714 162.277c0 7.333 7.918 13.277 17.686 13.277s17.687-5.944 17.687-13.277c0-7.333-7.919-13.277-17.687-13.277S714 154.944 714 162.277z"
        class="cloud1"
        clip-rule="evenodd"
      />
      <path
        fill-rule="evenodd"
        d="M649.792 115c8.215 0 15.361 3.695 19.075 9.147a23.42 23.42 0 013.04-.21c9.745 0 17.644 5.931 17.644 13.246s-7.9 13.245-17.644 13.245c-.117 0-.23-.011-.346-.013-3.495.035-21.1-.012-21.769-.012-12.035 0-21.792-7.925-21.792-17.7 0-9.775 9.757-17.7 21.792-17.7"
        class="cloud1"
        clip-rule="evenodd"
      />
      <path
        fill-rule="evenodd"
        d="M-60.475 164.311c2.526.02 7.307 1.122 13.52 2.97a26.9 26.9 0 01-4.51-14.659c0-18.569 19.968-33.622 44.601-33.622s44.6 15.053 44.6 33.622v.03c6.469-2.352 11.817-3.751 15.289-3.751 22.809 0 41.3 13.609 41.3 30.4 0 16.791-18.49 30.4-41.3 30.4h-2.72a2.904 2.904 0 01-.83.173c-.95.062-109.437-.139-110.41-.147-16.18-.131-29.192-11.492-29.064-23.644.128-12.152 13.352-21.9 29.53-21.766"
        class="cloud2"
        clip-rule="evenodd"
      />
    </g>
    <!-- end clouds-l -->
  {:else}
    <!-- start Stars -->
    <g fill-rule="evenodd" clip-rule="evenodd">
      <path
        fill="#FFDB56"
        fill-rule="evenodd"
        d="M114.767 175.021l-3.871-2.8-4.5 1.6 1.465-4.547-2.914-3.785 4.777-.011 2.7-3.941 1.487 4.54 4.582 1.349-3.858 2.817.133 4.775"
        class="star"
        clip-rule="evenodd"
      />
      <path
        fill="#A76965"
        fill-rule="evenodd"
        d="M177.933 156.065l-.565-6.721-5.856-3.344 6.217-2.61 1.371-6.6 4.407 5.1 6.7-.737-3.494 5.769 2.772 6.148-6.566-1.539-4.99 4.536"
        class="star1"
        clip-rule="evenodd"
      />
      <path
        fill="#FFECB0"
        fill-rule="evenodd"
        d="M129.482 125.218l-2.966-.015-1.694 2.434-.9-2.825-2.839-.859 2.409-1.731-.061-2.965 2.391 1.755 2.8-.973-.931 2.816 1.792 2.363h-.001z"
        class="star2"
        clip-rule="evenodd"
      />
      <path
        fill="#FFECB0"
        fill-rule="evenodd"
        d="M364.823 164.39l-4.862-.793-3.409 3.555-.748-4.869-4.435-2.144 4.4-2.216.669-4.88 3.466 3.5 4.848-.872-2.256 4.378 2.327 4.341z"
        class="star"
        clip-rule="evenodd"
      />
      <path
        fill="#A7903A"
        fill-rule="evenodd"
        d="M544.049 142.263l-4.555-4.229-6.066 1.356 2.614-5.638-3.162-5.35 6.17.744 4.111-4.662 1.2 6.1 5.7 2.47-5.429 3.025-.585 6.187.002-.003z"
        class="star1"
        clip-rule="evenodd"
      />
      <path
        fill="#AC953F"
        fill-rule="evenodd"
        d="M286.406 133.769l-5.068-2.442-4.885 2.79.757-5.574-4.163-3.784 5.535-1 2.312-5.128 2.665 4.955 5.591.614-3.888 4.064 1.144 5.508v-.003z"
        class="star2"
        clip-rule="evenodd"
      />
      <path
        fill="#ECC949"
        fill-rule="evenodd"
        d="M391.546 117.348l-3.675-.019-2.1 3.016-1.117-3.5-3.517-1.064 2.984-2.145-.075-3.673 2.961 2.175 3.47-1.206-1.153 3.488 2.22 2.928"
        class="star"
        clip-rule="evenodd"
      />
      <path
        fill="#FFECB0"
        fill-rule="evenodd"
        d="M608.615 131.529l-3.734-.609-2.618 2.73-.574-3.739-3.405-1.646 3.378-1.7.514-3.747 2.662 2.687 3.723-.67-1.733 3.363 1.787 3.333"
        class="star1"
        clip-rule="evenodd"
      />
      <path
        fill="#A76965"
        fill-rule="evenodd"
        d="M596.626 172.655l-4.579-2.763-4.872 2.206 1.213-5.208-3.6-3.952 5.328-.456 2.644-4.648 2.081 4.926 5.238 1.079-4.043 3.5.593 5.315"
        class="star2"
        clip-rule="evenodd"
      />
      <path
        fill="#A76965"
        fill-rule="evenodd"
        d="M420.751 141.747l-2.748-1.708-2.964 1.295.776-3.141-2.148-2.419 3.227-.233 1.637-2.79 1.218 3 3.16.7-2.474 2.085.316 3.219v-.008z"
        class="star"
        clip-rule="evenodd"
      />
    </g>

    <!-- start clouds-d -->
    <g
      fill="#3B44A0"
      fill-rule="evenodd"
      clip-rule="evenodd"
      clip-path="url(#cloud-holder)"
    >
      <path
        fill-rule="evenodd"
        d="M653 168.003a21.372 21.372 0 0118.383 9.911 20.1 20.1 0 012.93-.227c9.391 0 17 6.425 17 14.351 0 7.926-7.612 14.352-17 14.352-.113 0-.222-.013-.334-.015-3.369.039-20.339-.012-20.979-.012-11.6 0-21-8.588-21-19.18s9.4-19.18 21-19.18z"
        class="cloud1"
        clip-rule="evenodd"
      />
      <path
        fill-rule="evenodd"
        d="M-36.271 171.594c2.152.017 6.225.955 11.516 2.529a22.915 22.915 0 01-3.841-12.485c0-15.816 17.008-28.638 37.987-28.638 20.979 0 37.987 12.822 37.987 28.638v.026c5.51-2 10.065-3.2 13.022-3.2 19.428 0 35.177 11.592 35.177 25.891 0 14.299-15.749 25.891-35.177 25.891h-2.316a2.446 2.446 0 01-.707.148c-.809.052-93.214-.118-94.044-.125-13.78-.112-24.864-9.789-24.755-20.139.109-10.35 11.372-18.652 25.153-18.54l-.002.004zM-102 191.415c0 6.084 6.569 11.015 14.673 11.015s14.673-4.931 14.673-11.015c0-6.084-6.569-11.015-14.673-11.015S-102 185.332-102 191.415z"
        class="cloud2"
        clip-rule="evenodd"
      />
    </g>
    <!-- end clouds-d -->
  {/if}

  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingDarkColor}
      d="M469.742 400.03h64.374v-78.227h-64.374v78.227z"
    />
    <path
      fill={buildingLight7Color}
      d="M486.341 337.48h10.289v-9.18h-10.289v9.18zm14.571 19.28h10.29v-9.18h-10.29v9.18zm0 19.29h10.29v-9.18h-10.29v9.18z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingDarkColor}
      d="M423.292 396.69h59.22v-59.73h-59.22v59.73z"
    />
    <path
      fill={buildingLight8Color}
      d="M441.962 352.31h8.199v-10.88h-8.199v10.88zm13.434 0h8.199v-10.88h-8.199v10.88zm-13.434 17.56h8.199v-10.89h-8.199v10.89z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingLightColor}
      d="M199.793 403.35h73.531V268.046h-73.531V403.35z"
    />
    <path
      fill={buildingLight9Color}
      d="M222.974 291.4h9.575v-16.907h-9.575V291.4zm17.514 0h9.575v-16.907h-9.575V291.4zm17.514 0h9.575v-16.907h-9.575V291.4z"
    />
    <path
      fill={buildingLight2Color}
      d="M205.46 318.451h9.575v-16.907h-9.575v16.907z"
    />
    <path
      fill={buildingLight9Color}
      d="M222.974 318.451h9.575v-16.907h-9.575v16.907zm35.028 0h9.575v-16.907h-9.575v16.907zM240.488 345.5h9.575v-16.91h-9.575v16.91zm0 27.05h9.575v-16.91h-9.575v16.91zm17.514 0h9.575v-16.91h-9.575v16.91zm-35.028 27.05h9.575v-16.9h-9.575v16.9zm17.514 0h9.575v-16.9h-9.575v16.9zm17.514 0h9.575v-16.9h-9.575v16.9z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingMediumColor}
      d="M128.127 399.78H230.94v-66.97H128.127v66.97z"
    />
    <path
      fill={buildingLight7Color}
      d="M193.193 348.94h12.448v-8.74h-12.448v8.74zm-39.63 0h12.448v-8.74h-12.448v8.74zm-19.815 0h12.448v-8.74h-12.448v8.74zm79.261 20.64h12.448v-8.74h-12.448v8.74z"
    />
    <path
      fill={buildingLight6Color}
      d="M193.193 369.58h12.448v-8.74h-12.448v8.74z"
    />
    <path
      fill={buildingLight7Color}
      d="M173.378 369.58h12.448v-8.74h-12.448v8.74zm39.631 20.64h12.448v-8.74h-12.448v8.74zm-59.446 0h12.448v-8.74h-12.448v8.74zm-19.815 0h12.448v-8.74h-12.448v8.74z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingLightColor}
      d="M79.958 395.92h74.847V232.431H79.958V395.92z"
    />
    <path
      fill={buildingLight1Color}
      d="M120.588 252.08h10.345v-12.625h-10.345v12.625z"
    />
    <path
      fill={buildingLight9Color}
      d="M103.131 274.117h10.345v-12.625h-10.345v12.625z"
    />
    <path
      fill={buildingLight6Color}
      d="M138.045 274.117h10.345v-12.625h-10.345v12.625z"
    />
    <path
      fill={buildingLight3Color}
      d="M120.588 296.153h10.345v-12.625h-10.345v12.625z"
    />
    <path
      fill={buildingLight9Color}
      d="M138.045 296.153h10.345v-12.625h-10.345v12.625zm-34.914 22.037h10.345v-12.625h-10.345v12.625zm0 22.04h10.345V327.6h-10.345v12.63z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingDarkColor}
      d="M300.96 395.92h59.22V285.686h-59.22V395.92z"
    />
    <path
      fill={buildingLight8Color}
      d="M324.125 301.324h12.89v-9.256h-12.89v9.256z"
    />
    <path
      fill={buildingLight1Color}
      d="M342.766 301.324h12.89v-9.256h-12.89v9.256z"
    />
    <path
      fill={buildingLight8Color}
      d="M305.484 318.617h12.89v-9.256h-12.89v9.256z"
    />
    <path
      fill={buildingLight4Color}
      d="M324.125 318.617h12.89v-9.256h-12.89v9.256z"
    />
    <path
      fill={buildingLight8Color}
      d="M342.766 318.617h12.89v-9.256h-12.89v9.256zm-37.282 17.293h12.89v-9.26h-12.89v9.26zm18.641 17.29h12.89v-9.25h-12.89v9.25zm-18.641 17.3h12.89v-9.26h-12.89v9.26zm18.641 0h12.89v-9.26h-12.89v9.26z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingMediumColor}
      d="M344.553 395.92h83.483v-69.83h-83.483v69.83z"
    />
    <path
      fill={buildingLight5Color}
      d="M351.132 347.26h9.558V333.8h-9.558v13.46z"
    />
    <path
      fill={buildingLight7Color}
      d="M369.521 347.26h9.557V333.8h-9.557v13.46z"
    />
    <path
      fill={buildingLight6Color}
      d="M369.521 367.45h9.557v-13.46h-9.557v13.46z"
    />
    <path
      fill={buildingLight7Color}
      d="M387.91 367.45h9.557v-13.46h-9.557v13.46zm-36.777 20.19h9.557v-13.46h-9.557v13.46zm36.777 0h9.557v-13.46h-9.557v13.46z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingLightColor}
      d="M393.531 406.67h48.528V247.775h-48.528V406.67z"
    />
    <path
      fill={buildingLight9Color}
      d="M398.837 269.232h8.207v-14.57h-8.207v14.57z"
    />
    <path
      fill={buildingLight6Color}
      d="M413.65 269.232h8.208v-14.57h-8.208v14.57z"
    />
    <path
      fill={buildingLight3Color}
      d="M398.837 293.516h8.207v-14.57h-8.207v14.57z"
    />
    <path
      fill={buildingLight9Color}
      d="M428.464 293.516h8.208v-14.57h-8.208v14.57zM413.65 317.8h8.208v-14.57h-8.208v14.57z"
    />
    <path
      fill={buildingLight1Color}
      d="M428.464 317.8h8.208v-14.57h-8.208v14.57z"
    />
    <path
      fill={buildingLight9Color}
      d="M398.837 342.08h8.207v-14.57h-8.207v14.57z"
    />
    <path
      fill={buildingLight6Color}
      d="M428.464 342.08h8.208v-14.57h-8.208v14.57z"
    />
    <path
      fill={buildingLight9Color}
      d="M398.837 366.37h8.207V351.8h-8.207v14.57zm14.813 0h8.208V351.8h-8.208v14.57z"
    />
  </g>
  <path
    fill={buildingLight6Color}
    fill-rule="evenodd"
    d="M579.6 261.301h12.906v-14.058H579.6v14.058z"
    clip-rule="evenodd"
  />
  <path
    fill={buildingLight1Color}
    fill-rule="evenodd"
    d="M597.018 281.653h12.906v-14.059h-12.906v14.059z"
    clip-rule="evenodd"
  />
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingDarkColor}
      d="M555.484 395.92h78.549V239.776h-78.549V395.92z"
    />
    <path
      fill={buildingLight8Color}
      d="M562.125 261.301h12.906v-14.058h-12.906v14.058zM614.464 261.301h12.906v-14.058h-12.906v14.058zM579.6 281.653h12.906v-14.059H579.6v14.059zM562.125 302.004h12.906v-14.058h-12.906v14.058zm34.893 0h12.906v-14.058h-12.906v14.058zm-17.418 0h12.906v-14.058H579.6v14.058zm-17.475 40.706h12.906v-14.06h-12.906v14.06z"
    />
    <path
      fill={buildingLight4Color}
      d="M597.018 342.71h12.906v-14.06h-12.906v14.06z"
    />
    <path
      fill={buildingLight8Color}
      d="M562.125 363.06h12.906V349h-12.906v14.06zm34.893 20.35h12.906v-14.06h-12.906v14.06z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingDarkColor}
      d="M122.024 402.86h55.653v-95.543h-55.653v95.543z"
    />
    <path
      fill={buildingLight8Color}
      d="M157.75 327.73h9.453v-13h-9.453v13zm-15.15 0h9.452v-13H142.6v13z"
    />
    <path fill={buildingLight6Color} d="M157.75 349.57h9.453v-13h-9.453v13z" />
    <path
      fill={buildingLight8Color}
      d="M127.449 349.57h9.452v-13h-9.452v13zm30.301 21.84h9.453V358.4h-9.453v13.01zm-15.15 0h9.452V358.4H142.6v13.01zm0 21.83h9.452v-13H142.6v13zm-15.151 0h9.452v-13h-9.452v13z"
    />
  </g>
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingMediumColor}
      d="M263.36 410.64h47.256v-94.277H263.36v94.277z"
    />
    <path
      fill={buildingLight7Color}
      d="M295.713 338.68h7.954v-12.83h-7.954v12.83z"
    />
    <path
      fill={buildingLight6Color}
      d="M282.964 338.68h7.954v-12.83h-7.954v12.83z"
    />
    <path
      fill={buildingLight1Color}
      d="M295.713 360.23h7.954v-12.84h-7.954v12.84z"
    />
    <path
      fill={buildingLight7Color}
      d="M270.215 360.23h7.954v-12.84h-7.954v12.84zm25.498 21.54h7.954v-12.83h-7.954v12.83z"
    />
    <path
      fill={buildingLight5Color}
      d="M282.964 381.77h7.954v-12.83h-7.954v12.83z"
    />
  </g>
  <path
    fill={buildingLight7Color}
    fill-rule="evenodd"
    d="M282.964 403.32h7.954v-12.83h-7.954v12.83zm-12.749 0h7.954v-12.83h-7.954v12.83z"
    clip-rule="evenodd"
  />
  <g fill-rule="evenodd" clip-rule="evenodd">
    <path
      fill={buildingLightColor}
      d="M528.536 413.15h62.568V306.764h-62.568V413.15z"
    />
    <path
      fill={buildingLight9Color}
      d="M536.268 328.56h10.986v-12.982h-10.986v12.982zm0 21.83h10.986v-12.98h-10.986v12.98zm18.652 0h10.986v-12.98H554.92v12.98zm-18.652 21.82h10.986v-12.98h-10.986v12.98zm18.652 0h10.986v-12.98H554.92v12.98zm-20.083 21.87h10.986v-12.99h-10.986v12.99zm20.083 21.81h10.986V402.9H554.92v12.99z"
    />
    <path
      fill={buildingLight6Color}
      d="M573.073 328.56h10.986v-12.982h-10.986v12.982z"
    />
    <path
      fill={buildingLight9Color}
      d="M573.073 350.39h10.986v-12.98h-10.986v12.98zm-1.431 43.69h10.986v-12.99h-10.986v12.99z"
    />
  </g>
  <path
    fill={windowFrameColor}
    fill-rule="evenodd"
    d="M468.463 394.39h22.978V55.793h-22.978V394.39zm-238.713 0h22.978V55.793H229.75V394.39z"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameColor}
    fill-rule="evenodd"
    d="M625.957 91.815V390.51H95.409V59.969H65.946V417.8H655.42V59.969h-29.463v31.846z"
    clip-rule="evenodd"
  />
  <path
    fill="#CBCBCB"
    fill-rule="evenodd"
    d="M65.858 75.958h589.475V52.657H65.858v23.301z"
    clip-rule="evenodd"
  />
  <path
    fill="#629E04"
    fill-rule="evenodd"
    d="M517.245 368.44c-.485-2.39-1.114-4.75-1.963-6.98a41.33 41.33 0 00-4.447-8.5c-.802-1.18-5.782-5.73-5.648-6.77.107-.83 1.257-1.34 2.246-1.23.988.11 1.824.65 2.584 1.19 6.216 4.43 9.636 11.12 10.969 17.71.362.21.761-.22.895-.57 2.324-6.09 1.322-13.21-.001-19.36-1.644-7.65-2.508-15.42-7.491-22.25-.543-.744-1.135-1.705-.542-2.423.479-.581 1.545-.623 2.275-.271.73.351 1.194.985 1.594 1.607 2.336 3.634 3.592 8.407 4.836 12.427-.894-7.11 1.316-15.161 4.446-21.728.373-.785.822-1.614 1.687-2.046.865-.432 2.25-.201 2.493.619-2.735 5.295-4.916 11.29-5.901 16.985-1.26 7.29 1.006 13.59 1.667 20.77-.156-1.7 1.582-5.06 2.067-6.85.701-2.58 2.458-4.78 4.83-6.55.617-.46 1.317-.9 2.137-.98.819-.08 1.76.34 1.866 1.02.112.73-.671 1.3-1.336 1.77-5.708 4.05-7.788 10.69-8.191 16.95-.517 8.03.685 15.88-1.797 23.77-.202.64-.426 1.3-.891 1.84-1.452 1.69-4.441 1.54-6.889 1.22-.329-3.69-.731-7.58-1.495-11.37"
    clip-rule="evenodd"
  />
  <path
    fill="#AFCC05"
    fill-rule="evenodd"
    d="M507.12 326.95c6.443 3.8 6.486 11.88 2.136 19.26-4.351 7.38-11.448 11.26-17.891 7.46-6.443-3.8-5.441-21.22-5.441-21.22s14.753-9.301 21.196-5.5"
    clip-rule="evenodd"
  />
  <path
    fill="#629E04"
    fill-rule="evenodd"
    d="M509.256 346.21c-4.351 7.38-11.448 11.26-17.891 7.46-6.443-3.8-5.441-21.22-5.441-21.22s23.448 13.74 23.332 13.76"
    clip-rule="evenodd"
  />
  <path
    fill="#AFCC05"
    fill-rule="evenodd"
    d="M533.58 319.805c-4.629 4.157-3.335 10.755 1.424 16.055 4.76 5.3 11.183 7.3 15.812 3.14s.95-18.189.95-18.189-13.558-5.162-18.186-1.006z"
    clip-rule="evenodd"
  />
  <path
    fill="#629E04"
    fill-rule="evenodd"
    d="M535.004 335.86c4.76 5.3 11.183 7.3 15.812 3.14s.95-18.189.95-18.189-16.859 15.059-16.762 15.049"
    clip-rule="evenodd"
  />
  <path
    fill="#AFCC05"
    fill-rule="evenodd"
    d="M520.718 307.381c2.849 4.448.299 9.557-4.794 12.819-5.093 3.263-10.8 3.443-13.649-1.005-2.849-4.447 3.332-15.101 3.332-15.101s12.262-1.16 15.111 3.287z"
    clip-rule="evenodd"
  />
  <path
    fill="#629E04"
    fill-rule="evenodd"
    d="M515.924 320.2c-5.093 3.263-10.8 3.443-13.649-1.005-2.849-4.447 3.332-15.101 3.332-15.101l10.317 16.106z"
    clip-rule="evenodd"
  />
  <path
    fill="#AFCC05"
    fill-rule="evenodd"
    d="M524.54 300.538c-2.303 3.763-.086 7.986 4.223 10.623 4.309 2.637 9.078 2.69 11.381-1.073 2.303-3.762-3.041-12.553-3.041-12.553s-10.26-.759-12.563 3.003"
    clip-rule="evenodd"
  />
  <path
    fill="#629E04"
    fill-rule="evenodd"
    d="M528.763 311.161c4.309 2.637 9.078 2.69 11.381-1.073 2.303-3.762-3.041-12.553-3.041-12.553l-8.34 13.626"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLinesColor}
    fill-rule="evenodd"
    d="M501.017 367.62s.76 16.84 11.091 36.06h22.859c10.331-19.22 11.092-36.06 11.092-36.06h-45.042"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameColor}
    fill-rule="evenodd"
    d="M534.299 367.62h-33.282s.609 13.35 8.031 29.84l.19.06c11.958 4.72 21.936-8.59 25.061-29.9z"
    clip-rule="evenodd"
  />
  <path
    fill="#E7FFFF"
    fill-rule="evenodd"
    d="M77.559 80.412h566.026V57.111H77.559v23.301z"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLighterColor}
    fill-rule="evenodd"
    d="M2.18 94.037h715.64V78.751H2.18v15.286z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M2.18 94.037v1.362h717.002v-18.01H.818v18.01H2.18v-1.362h1.361V80.113h712.917v12.563H2.18v1.361h1.361H2.18z"
    clip-rule="evenodd"
  />
  {#if isBlinderClosed}
    {#each [...Array(25).keys()] as i}
      <g out:fly={{ duration: 500, y: -10, delay: 50 * (25 - i) }}>
        <path fill={windowColor} d="M2 {i * 11 + 117}h716v-10H2z" />
        <path
          fill="#B3D3DC"
          d="M2.361 {i * 11 + 118}.169V{i * 11 +
            117}H719v-11H1v11h1.361v-.831h1.36v-8.506h712.556v7.674H2.361v.832h1.36-1.36"
        />
        <path
          fill="#B3D3DC"
          d="M136 {i * 11 + 117}h3v-11h-3zM584 {i * 11 + 117}h3v-11h-3z"
        />
      </g>
    {/each}
  {/if}
  <path
    fill={windowFrameLighterColor}
    fill-rule="evenodd"
    d="M2.18 82.92h715.64V67.634H2.18V82.92z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M2.18 82.92v1.362h717.002v-18.01H.818v18.01H2.18V82.92h1.361V68.996h712.917v12.562H2.18v1.362h1.361H2.18"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLighterColor}
    fill-rule="evenodd"
    d="M2.18 71.803h715.64V56.517H2.18v15.286z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M2.18 71.803v1.362h717.002v-18.01H.818v18.01H2.18v-1.362h1.361V57.878h712.917v12.563H2.18v1.362h1.361H2.18z"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLighterColor}
    fill-rule="evenodd"
    d="M2.18 60.686h715.64V45.399H2.18v15.287z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M2.18 60.686v1.361h717.002V44.038H.818v18.009H2.18v-1.361h1.361V46.761h712.917v12.563H2.18v1.362h1.361H2.18"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLighterColor}
    fill-rule="evenodd"
    d="M2.18 49.568h715.64V34.282H2.18v15.286z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M2.18 49.568v1.362h717.002V32.92H.818v18.01H2.18v-1.362h1.361V35.644h712.917v12.563H2.18v1.361h1.361H2.18z"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLighterColor}
    fill-rule="evenodd"
    d="M2.18 38.451h715.64V23.165H2.18v15.286z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M2.18 38.451v1.362h717.002v-18.01H.818v18.01H2.18v-1.362h1.361V24.527h712.917v12.562H2.18v1.362h1.361H2.18z"
    clip-rule="evenodd"
  />
  <path
    fill={windowColor}
    fill-rule="evenodd"
    d="M2.18 26.772h715.64V1.758H2.18v25.014z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M2.18 26.772v1.362h717.002V.397H.818v27.737H2.18v-1.362h1.361V3.12h712.917v22.29H2.18v1.362h1.361H2.18z"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLighterColor}
    fill-rule="evenodd"
    d="M683.14 341.54h6.08V24.987h-6.08V341.54z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M683.14 341.54v1.04h7.122V23.944h-8.164V342.58h1.042v-1.04h1.043V26.029h3.995V340.5h-5.038v1.04h1.043-1.043z"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLighterColor}
    fill-rule="evenodd"
    d="M692.348 345.05c0 1.636-.65 3.205-1.807 4.361a6.165 6.165 0 01-8.722 0 6.165 6.165 0 01-1.807-4.361v-12.7c0-3.4 2.762-6.17 6.168-6.17a6.173 6.173 0 016.168 6.17v12.7z"
    clip-rule="evenodd"
  />
  <path
    fill="#8BADB6"
    fill-rule="evenodd"
    d="M692.348 345.05h-1.042a5.131 5.131 0 01-1.501 3.63 5.143 5.143 0 01-3.625 1.5 5.14 5.14 0 01-3.624-1.5 5.13 5.13 0 01-1.501-3.63v-12.7c0-1.42.572-2.69 1.501-3.62a5.087 5.087 0 013.624-1.5 5.108 5.108 0 013.625 1.5c.929.93 1.5 2.2 1.501 3.62v12.7h2.084v-12.7a7.21 7.21 0 00-14.42 0v12.7a7.21 7.21 0 0014.42 0h-1.042"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLinesColor}
    fill-rule="evenodd"
    d="M2.18 26.123h715.64v-5.559H2.18v5.559z"
    clip-rule="evenodd"
  />
  <path
    fill={windowFrameLinesColor}
    fill-rule="evenodd"
    d="M136.116 94.464h2.575V23.128h-2.575v71.336zm448.35 0h2.575V23.128h-2.575v71.336z"
    clip-rule="evenodd"
  />
</svg>

<style>
  @keyframes star {
    to {
      transform: scale(0.8);
      opacity: 0.2;
    }
    from {
      transform: scale(1);
      opacity: 1;
    }
  }
  @keyframes star1 {
    to {
      opacity: 0.2;
      transform: scale(0.9);
    }
    from {
      opacity: 1;
      transform: scale(1);
    }
  }
  @keyframes star2 {
    0% {
      opacity: 1;
    }
    45% {
      opacity: 1;
    }
    55% {
      opacity: 0.2;
    }
    100% {
      opacity: 0.2;
    }
  }
  svg .star {
    animation-name: star;
    animation-timing-function: ease-in-out;
    animation-iteration-count: infinite;
    animation-duration: 2s;
    animation-direction: alternate;
    transform-box: fill-box;
  }
  svg .star1 {
    animation-name: star1;
    animation-timing-function: ease-in-out;
    animation-iteration-count: infinite;
    animation-duration: 3s;
    animation-direction: alternate;
    transform-box: fill-box;
  }
  svg .star2 {
    animation-name: star2;
    animation-timing-function: ease-in-out;
    animation-iteration-count: infinite;
    animation-duration: 5s;
    animation-direction: alternate;
    transform-box: fill-box;
  }
  @keyframes back-cloud-move {
    from {
      transform: translate(0);
    }
    to {
      transform: translate(720px);
    }
  }
  @keyframes cloud-move {
    to {
      transform: translate(-720px);
    }
    from {
      transform: translate(0);
    }
  }
  svg .cloud1 {
    animation-name: cloud-move;
    animation-duration: 70s;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
  }
  svg .cloud2 {
    animation-name: back-cloud-move;
    animation-duration: 70s;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
  }
  @keyframes moon {
    50% {
      transform: translatey(-5%);
    }
  }
  @keyframes jam {
    50% {
      transform: translatey(-2%);
    }
  }
  svg .moon,
  svg .sun {
    animation: moon 2000ms 500ms ease-in-out infinite;
    transform-box: fill-box;
  }
  svg .jamming {
    animation: jam 2000ms 500ms ease-in-out infinite;
    transform-box: fill-box;
  }
</style>
