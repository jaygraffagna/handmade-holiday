<script>
  import { onMount, tick } from 'svelte';
  import Cubs from '../components/Cubs.svx'

  let canvas;
  let context;

  const draw = () => {
    context = canvas.getContext("2d");
    const cWidth = canvas.width;
    const cHeight = canvas.height;    

    context.beginPath();
    context.fillStyle = "#ffffff";
    context.arc(cWidth/2, cHeight/2,  cHeight/2, 0, 2*Math.PI);
    context.fill();

    context.beginPath();
    context.fillStyle = "#0e3286";
    context.arc(cWidth/2, cHeight/2, (cHeight/2)-5, 0, 2*Math.PI);
    context.fill();

    context.beginPath();
    context.fillStyle = "#ffffff";
    context.arc(cWidth/2, cHeight/2,  (cHeight/2)-25, 0, 2*Math.PI);
    context.fill();

    context.beginPath();
    context.fillStyle = "#cc3433";
    context.arc(cWidth/2, cHeight/2,  (cHeight/2)-30, .35*Math.PI, 1.65*Math.PI);
    context.fill();

    context.beginPath();
    context.fillStyle = "#ffffff";
    context.arc(cWidth/2, cHeight/2,  (cHeight/2)-50, 0, 2*Math.PI);
    context.fill();

    context.font = "900 28px sans-serif"; 
    context.fillStyle = "#cc3433";
    context.fillText("UBS", 130, 85);
  }

  onMount(async () => {
    await tick()
    draw();
  });
</script>
<style>
  canvas {
    position: absolute;
    top: 35%;
    left: 3%;
    width: 400px;
    height: 200px;
  }
  #wrapper{
    position: relative;
    font-size: 10px;
  }

  @media (max-width: 500px) {
      canvas {
        position: absolute;
        top: 30%;
        left: 3%;
        width: 300px;
        height: 150px;
      }
      #wrapper{
        position: relative;
        font-size: 7px;
      }
  }
</style>

<svelte:head>
  <title>Grant</title>
</svelte:head>

<div id="wrapper" class="container">
  <h1>Grant</h1>
  <Cubs/>
  <canvas bind:this={canvas} />
</div>
