<script>
  import { onMount, tick } from 'svelte';
  import Marmion from '../components/Marmion.svx'

  let canvas;
  let context;

  const draw = () => {
    context = canvas.getContext("2d");
     
    context.font = "900 120px Serif"; context.fillStyle = "#bC222a";
    context.fillText("M A", 40, 100);
    context.font = "900 115px Serif"; context.fillStyle = "#1a2753";
    context.fillText("M A", 40, 100);

    context.fillStyle = "gray";  context.fillRect(175, 85, 50, 40);

    let stick = new Path2D();
    stick.moveTo(200, 90); stick.lineTo(140, 130);
    stick.lineTo(100, 130); stick.lineTo(100, 136); 
    stick.lineTo(140, 136); stick.lineTo(205, 92);
    context.fillStyle = "#1a2753"; 
    context.fill(stick);

    context.fillStyle = "#bC222a"; 
    context.fillRect(108, 130, 25, 6);

    let tape = new Path2D();
    tape.moveTo(200, 90); tape.lineTo(188, 98);
    tape.lineTo(193, 100); tape.lineTo(205, 92);
    context.fillStyle = "#bC222a"; context.fill(tape);
  }

  onMount(async () => {
    await tick()
    draw();
  });
</script>
<style>
  canvas {
    position: absolute;
    top: 15%;
    left: 3%;
    width: 400px;
    height: 395px;
  }
  #wrapper{
    position: relative;
    font-size: 10px;
  }

  @media (max-width: 500px) {
      canvas {
        position: absolute;
        top: 22%;
        left: 3.5%;
        width: 275px;
        height: 275px;
      }
      #wrapper{
        position: relative;
        font-size: 7px;
      }
  }
</style>

<svelte:head>
  <title>Jack Wallace</title>
</svelte:head>

<div id="wrapper" class="container">
  <h1>Jack Wallace</h1>
  <Marmion/>
  <canvas bind:this={canvas} />
</div>
