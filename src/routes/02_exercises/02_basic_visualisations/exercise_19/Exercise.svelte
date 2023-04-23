<script>
    // Dimensions
    const width = 800;
    const height = 100;
    const margin = { top: 20, right: 5, bottom: 5, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    const values = [
      { x: 2, y: 1, category: "cat1" },
      { x: 4, y: 2, category: "cat3" },
      { x: 6, y: 1, category: "cat2" },
      { x: 7, y: 3, category: "cat3" },
      { x: 9, y: 1, category: "cat2" }
    ];

    import { scaleLinear} from 'd3-scale';
    const scaleX = scaleLinear().domain([1, 10]).range([0,innerWidth]);
    const scaleY = scaleLinear().domain([0, 4]).range([0,innerHeight]);

    import {scaleOrdinal} from "d3-scale";
    import {schemePastel1} from "d3-scale-chromatic"
    const uniques = [...new Set(values.map(v => v.category))]
    const ordinalScale = scaleOrdinal(schemePastel1)
      .domain(uniques);

  </script>
  
  <svg viewBox="0 0 {width} {height}">
    <g transform="translate({margin.left},{margin.top})">
      <!--  -->
      {#each values as value}
      <circle cx={scaleX(value.x)} cy={scaleY(value.y)} r="10" fill={ordinalScale(value.category)} />
      <text x={scaleX(value.x)} y={scaleY(value.y)-20} class="valueLabel"> {value.y} </text>
      {/each}
    </g>
  </svg>
  
  <style>
    text {
      text-anchor: middle;
      font-size: small;
    }
  </style>
  