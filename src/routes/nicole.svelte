<script>
  import { onMount, tick } from 'svelte';
  import Iowa from '../components/Iowa.svx'

  let canvas;
  let context;

  const draw = () => {
    context = canvas.getContext("2d");
    const cWidth = canvas.width;
    const cHeight = canvas.height;    

    context.fillStyle = "black";  
    context.fillRect(10, 40, 275, 70);

    context.fillStyle = "#fed602";  
    context.fillRect(20, 45, 255, 60);

    context.fillStyle = "black";  
    context.fillRect(30, 80, 235, 20);

    context.font = "900 italic 42px Verdana"; 
    context.fillStyle = "black";
    context.fillText("IOWA", 75, 78);

    context.font = "900 italic 28px Verdana"; 
    context.fillStyle = "#fed602";
    context.fillText("HAWKEYES", 60, 100);
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
  <title>Nicole</title>
</svelte:head>

<div id="wrapper" class="container">
  <h1>Nicole</h1>
  <Iowa/>
  <canvas bind:this={canvas} />
</div>
