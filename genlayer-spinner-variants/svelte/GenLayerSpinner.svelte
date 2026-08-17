<script>
  export let size = 48;
  export let speed = 1;
  export let accent = "#E66F00";
  export let ink = "currentColor";
  export let label = "Loading";

  const HEX = "M21.75 1.29904C23.1423 0.49519 24.8577 0.49519 26.25 1.29904L42.5346 10.701C43.9269 11.5048 44.7846 12.9904 44.7846 14.5981V33.4019C44.7846 35.0096 43.9269 36.4952 42.5346 37.299L26.25 46.701C24.8577 47.5048 23.1423 47.5048 21.75 46.701L5.46539 37.299C4.07309 36.4952 3.21539 35.0096 3.21539 33.4019V14.5981C3.21539 12.9904 4.07309 11.5048 5.46539 10.701L21.75 1.29904Z";
  const WL = "M22.724 19.0141C22.724 19.0696 22.7117 19.1244 22.6879 19.1746L18.3128 28.4118C18.2256 28.596 18.3014 28.8161 18.4835 28.9075L21.707 30.5252C21.9966 30.6705 21.978 31.09 21.6766 31.2091L11.3893 35.2736C11.0721 35.3989 10.7659 35.0703 10.9133 34.7628L22.0109 11.6127C22.1834 11.2528 22.724 11.3757 22.724 11.7748V19.0141Z";
  const WR = "M25.276 19.0141C25.276 19.0696 25.2883 19.1244 25.3121 19.1746L29.6872 28.4118C29.7744 28.596 29.6986 28.8161 29.5165 28.9075L26.293 30.5252C26.0034 30.6705 26.022 31.09 26.3234 31.2091L36.6107 35.2736C36.9279 35.3989 37.2341 35.0703 37.0867 34.7628L25.9891 11.6127C25.8166 11.2528 25.276 11.3757 25.276 11.7748V19.0141Z";
  const CR = "M23.6044 22.9593C23.7386 22.678 24.1376 22.6737 24.2778 22.9521L26.4398 27.2456C26.5335 27.4318 26.4575 27.6587 26.2705 27.7507L24.1044 28.8172C23.9971 28.87 23.8711 28.8685 23.7651 28.8131L21.7216 27.7455C21.5427 27.6521 21.4699 27.4338 21.5568 27.2517L23.6044 22.9593Z";
</script>

<svg
  class="gl-spinner"
  style="--gl-size:{size}px; --gl-speed:{speed}; --gl-accent:{accent}; --gl-ink:{ink}"
  viewBox="0 0 48 48"
  xmlns="http://www.w3.org/2000/svg"
  role="status"
  aria-label={label}
  width={size}
  height={size}
>
  <path class="gl-track" d={HEX} />
  <path class="gl-edge" d={HEX} pathLength="100" />
  <g class="gl-glyph">
    <path class="gl-wing" d={WL} />
    <path class="gl-wing" d={WR} />
    <path class="gl-core" d={CR} />
  </g>
</svg>

<style>
  svg :global(.gl-track) {
    fill: none;
    stroke: var(--ink, currentColor);
    stroke-width: 2.4;
    opacity: 0.16;
  }
  svg :global(.gl-edge) {
    fill: none;
    stroke: var(--acc, #E66F00);
    stroke-width: 2.4;
    stroke-linecap: round;
    animation: circuit calc(2s / var(--speed, 1)) linear infinite;
  }
  svg :global(.gl-wing) { fill: var(--ink, currentColor); }
  svg :global(.gl-core) { fill: var(--acc, #E66F00); }
  svg :global(.gl-glyph) {
    animation: breathe calc(2s / var(--speed, 1)) ease-in-out infinite;
  }
  @keyframes circuit {
    from { stroke-dasharray: 20 80; stroke-dashoffset: 0 }
    to   { stroke-dasharray: 20 80; stroke-dashoffset: -100 }
  }
  @keyframes breathe {
    0%, 100% { opacity: 0.45 }
    50%      { opacity: 1 }
  }
  @media (prefers-reduced-motion: reduce) {
    svg :global(.gl-edge) { stroke-dasharray: 24 76 !important; stroke-dashoffset: 0 !important; animation: none }
    svg :global(.gl-glyph) { opacity: 1 !important; animation: none }
  }
</style>
