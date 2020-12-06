<script>
  import { onMount, tick } from 'svelte';
  import TriforceCode from '../components/TriforceCode.svx'

  let canvas;
  let context;

  const draw = () => {
    context = canvas.getContext("2d");
    const cWidth = canvas.width;
    const cHeight = canvas.height;

    let triangle1 = new Path2D();
    triangle1.moveTo(cWidth * .5, 0);
    triangle1.lineTo(cWidth * .25, cHeight * .5);
    triangle1.lineTo(cWidth * .75, cHeight * .5);
    context.fillStyle = 'gold';
    context.fill(triangle1);

    let triangle2 = new Path2D();
    triangle2.moveTo(cWidth * .25,  cHeight * .5);
    triangle2.lineTo(0, cHeight);
    triangle2.lineTo(cWidth * .5, cHeight);
    context.fillStyle = 'gold';
    context.fill(triangle2);

    let triangle3 = new Path2D();
    triangle3.moveTo(cWidth * .75, cHeight * .5);
    triangle3.lineTo(cWidth * .5, cHeight);
    triangle3.lineTo(cWidth, cHeight);
    context.fillStyle = 'gold';
    context.fill(triangle3);
  }

  onMount(async () => {
    await tick()
    draw();
  });
</script>
<style>
  canvas {
    position: absolute;
    top: 22%;
    left: 3%;
    width: 400px;
    height: 300px;
  }
  #wrapper{
    position: relative;
    font-size: 10px;
  }

  @media (max-width: 500px) {
      canvas {
        position: absolute;
        top: 22%;
        left: 3%;
        width: 200px;
        height: 150px;
      }
      #wrapper{
        position: relative;
        font-size: 5px;
      }
  }
</style>

<svelte:head>
  <title>Lucas</title>
</svelte:head>

<div id="wrapper" class="container">
  <h1>Lucas</h1>
  <TriforceCode id="code"/>
  <canvas bind:this={canvas} />
</div>
