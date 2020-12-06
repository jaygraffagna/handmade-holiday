<style>
  .home-container {
    align-items: center;
    display: flex;
    flex: 1;
    justify-content: center;
    margin: 2em 0;
    min-height: 400px;
  }

  .home-copy {
    flex: 1;
  }

  h1 {
    font-weight: 600;
    margin-bottom: 0.5em;
    color: #fd6378;
  }

  p {
    font-size: 1.4em;
    line-height: 1.5;
  }

  figure {
    margin: 0 1em;
    text-align: center;
  }

  figcaption {
    font-size: .8em;
    font-style: italic;
  }

  img {
    width: 300px;
    max-width: 300px;
  }

  @media (max-width: 1020px) {
    p {
      font-size: 1.2em;
    }

    img {
      max-width: 300px;
    }
  }

  @media (max-width: 800px) {
    .home-container {
      flex-direction: column;
    }

    .home-copy {
      flex: 0;
      padding-bottom: 2em;
      text-align: center;
    }
  }
</style>

<svelte:head>
  <title>Jay's Handmade Holiday</title>
</svelte:head>

<div class="home-container">
  <div class="home-copy">
    <h1>Welcome to Jay's Handmade Holiday!</h1>
    <p>Check out the different handmade made gifts for the family</p>
  </div>

  <figure>
    <img alt='Snowflake' src='snowflake.svg'>
  </figure>
</div>
