<script lang="typescript">
  import { onMount, beforeUpdate } from "svelte";
  import { range } from "lodash";

  export let innerWidth;
  export let innerHeight = 600;

  class Star {
    _x: number;
    _y: number;
    _radius: number;
    _c: CanvasRenderingContext2D;

    constructor(
      x: number,
      y: number,
      radius: number,
      c: CanvasRenderingContext2D
    ) {
      this._x = x;
      this._y = y;
      this._radius = radius;
      this._c = c;
    }

    draw() {
      const grad = this.genGradient(Boolean(Math.round(Math.random() * 1)));

      this._c.beginPath();
      this._c.arc(this._x, this._y, this._radius, 0, Math.PI * 2, false);
      this._c.fillStyle = grad;
      this._c.fill();
    }

    private genGradient(dark = false) {
      const gradRadius = Math.ceil(this._radius / 3);
      // Create gradient
      const grad = this._c.createRadialGradient(
        gradRadius,
        gradRadius,
        0,
        gradRadius,
        gradRadius,
        gradRadius
      );
      // Add colors
      grad.addColorStop(0.315, "#dbdbdb");
      grad.addColorStop(0.878, "#ffffff");

      if (dark) {
        grad.addColorStop(0.315, "black");
        grad.addColorStop(0.878, "gray");
      }

      return grad;
    }
  }

  const renderStars = () => {
    const domCanvas = document.querySelector("canvas");
    domCanvas && (domCanvas.width = innerWidth);
    domCanvas && (domCanvas.height = innerHeight);

    const ctx = domCanvas?.getContext("2d");
    if (ctx) {
      range(0, innerWidth / 2).forEach((_i) => {
        const maxWidth = Math.random() * innerWidth;
        const maxHeight = Math.random() * innerHeight;
        const radius = Math.random() * 1.5;
        const star = new Star(maxWidth, maxHeight, radius, ctx);
        star.draw();
      });
    }
  };

  onMount(renderStars);
  beforeUpdate(renderStars);
</script>

<style>
  div {
    position: absolute;
    z-index: -10;
  }
</style>


<div>
  <canvas />
</div>
