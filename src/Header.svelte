<script>
  import { slide } from "svelte/transition";
  let isMobile = false;
  let innerWidth;

  $: isMobile = innerWidth < 840 ? true : false;
</script>

<header>
  <div>
    <h1>
      <img
        src="https://highlandsmotoringfestival.com/wp-content/uploads/highlands-motoring-festival.png"
        alt="Logo"
      />
    </h1>
    <i on:click={() => (isMobile = !isMobile)} class="fa fa-bars" />
  </div>
  {#if !isMobile}
    <nav transition:slide>
      <a href="#about">About</a>
      <a href="#events">Events</a>
      <a href="#gallery">Gallery</a>
      <a href="#contact">Contact</a>
    </nav>
  {/if}
</header>

<svelte:window bind:innerWidth />

<svelte:head
  ><link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"
    integrity="sha512-iBBXm8fW90+nuLcSKlbmrPcLa0OT92xO1BIsZ+ywDWZCvqsWgccV3gFoRBv0z+8dLJgyAHIhR35VZc2oM/gI1w=="
    crossorigin="anonymous"
  /></svelte:head
>

<style>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 2em;
    margin: 0;
    padding: 2em 3em;
    background-image: radial-gradient(#1a6626, #154e1c);
    color: white;
  }
  div img {
    width: 50%;
  }
  nav {
    display: flex;
    gap: 2em;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }
  a {
    display: block;
    line-height: 2.5em;
    text-align: center;
    font-weight: bold;
    color: white;
    text-decoration: none;
  }
  a:hover {
    color: gold;
  }
  i {
    display: none;
  }
  @media (max-width: 840px) {
    header {
      flex-direction: column;
      align-items: stretch;
      padding: 2em;
      line-height: 1em;
    }
    div {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    div img {
      width: 100px;
    }
    nav {
      display: block;
      width: 100%;
    }
    i {
      display: block;
      font-size: 2em;
    }
  }
</style>
