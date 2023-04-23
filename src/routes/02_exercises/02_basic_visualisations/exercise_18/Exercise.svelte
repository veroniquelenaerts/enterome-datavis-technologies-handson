<script>
  // Dimensions
  const width = 800;
  const height = 100;
  const margin = { top: 5, right: 5, bottom: 5, left: 5 };
  const innerWidth = width - margin.left - margin.right;
  const innerHeight = height - margin.top - margin.bottom;

  // Array
  const values = [2, 4, 6, 7, 9];

  import { scaleLog} from 'd3-scale';
  const scale = scaleLog().domain([1, 10]).range([0,innerWidth]);
  
  import { axisBottom } from 'd3-axis';
  
  import { select } from 'd3-selection'

  function xAxisBuilder(handle) {
      const xAxis = axisBottom(scale)
      xAxis(select(handle))
    }


</script>

<svg viewBox="0 0 {width} {height}">
  <g transform="translate({margin.left},{margin.top})">
    <!--  -->
    {#each values as value}
      <circle cx={scale(value)} cy={innerHeight/2} r="10" fill="teal" />
    {/each}
  </g>
  <g use:xAxisBuilder transform="translate({0},{innerHeight/2})">
    <text fill="currentColor" x={innerWidth/2} y=-4 > x-axis </text>
  </g>
</svg>
