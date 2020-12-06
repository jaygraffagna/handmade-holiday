<script>
  export let segment;
</script>

<style>
  nav {
    align-items: flex-end;
    display: flex;
    flex: 1;
    font-family: Rubik, sans-serif;
    font-weight: 700;
    justify-content: flex-end;
    text-transform: uppercase;
  }

  a {
    color: inherit;
    text-decoration: none;
    padding: 10px 5px;
    display: block;
    position: relative;
    margin-left: 20px;
  }

  a:not(.selected) {
    opacity: 0.7;
  }

  a::before {
    content: '';
    position: absolute;
    transition: transform .3s ease;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 2px;
    background: #AAA;
    transform: scaleX(0);
  }

  a:hover::before,
  .selected::before {
    transform: scaleX(1);
  }

  .selected::before {
    background: #fd6378;
  }

  @media (max-width: 500px) {
      nav {
      flex-direction: column;
      align-items: flex-end;
      display: flex;
      flex: 1;
      font-family: Rubik, sans-serif;
      font-weight: 700;
      justify-content: flex-end;
      text-transform: uppercase;
    }
  }
</style>

<nav>
  <a class='{segment === undefined ? "selected" : ""}' href='.'>Home</a>
  <a class='{segment === "grant" ? "selected" : ""}' href='grant'>Grant</a>
  <a class='{segment === "nicole" ? "selected" : ""}' href='nicole'>Nicole</a>
  <a class='{segment === "jackwallace" ? "selected" : ""}' href='jackwallace'>Jack Wallace</a>
  <a class='{segment === "lucas" ? "selected" : ""}' href='lucas'>Lucas</a>
</nav>
