//HTML NYA -----------------------------------------------------------

<svg viewBox="0 0 800 600">
  <symbol id="s-text">
    <text text-anchor="middle"
          x="50%"
          y="35%"
          class="text--line"
          >
      Ardisca
    </text>
    <text text-anchor="middle"
          x="50%"
          y="68%"
          class="text--line2"
          >
      IDC
    </text>
    
  </symbol>
  
  <g class="g-ants">
    <use xlink:href="#s-text"
      class="text-copy"></use>     
    <use xlink:href="#s-text"
      class="text-copy"></use>     
    <use xlink:href="#s-text"
      class="text-copy"></use>     
    <use xlink:href="#s-text"
      class="text-copy"></use>     
    <use xlink:href="#s-text"
      class="text-copy"></use>     
  </g>
  
  
</svg>

//CSS NYA DIBAWAH-------------------------------------------------------------------------


HTML, BODY {
  height: 100%;
  }

$colors: #360745, #D61C59, #E7D84B, #EFEAC5, #1B8798;

BODY {
  background: hsl(200,70,11);
  background-size: .12em 100%;
  font: 16em/1 Arial;
}

.text--line {
  font-size: .5em;
  }

svg {
  position: absolute;
  width: 100%;
  height: 100%;
  }

$max: 5;
$stroke-step: 7%; 
.text-copy {
  fill: none;
  stroke: white;
  stroke-dasharray: $stroke-step $stroke-step * ($max - 1);
  stroke-width: 3px;
  
  animation: stroke-offset 9s infinite linear;
  
  @for $item from 1 through $max {
    $stroke-color: nth($colors, $item);
    
    &:nth-child(#{$item}) {
      stroke: $stroke-color;
      stroke-dashoffset: $stroke-step * $item;
      }
    }
  }

@keyframes stroke-offset {
  50% {
    stroke-dashoffset: $stroke-step * $max;  
    stroke-dasharray: 0 $stroke-step * $max*2.5;
  }
}

