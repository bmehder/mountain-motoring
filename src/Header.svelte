<script>
  import { slide } from 'svelte/transition'
  let isMobile = false
  let innerWidth

  $: isMobile = innerWidth < 840 ? true : false
</script>

<header>
  <div>
    <!-- <h1>
      <a href="https://highlandsmotoringfestival.com/" target="_blank">
        <img
          src="https://highlandsmotoringfestival.com/wp-content/uploads/highlands-motoring-festival.png"
          alt="Logo"
        /></a
      >
    </h1> -->
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
  />
</svelte:head>

<style>
  header {
    display: flex;
    justify-content: space-between;
    justify-content: center;
    align-items: center;
    gap: 2em;
    margin: 0;
    padding: 2em 3em;
    background: #00525c;
    color: white;
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
    font-size: 1.5em;
    font-weight: bold;
    color: white;
    text-decoration: none;
  }
  a:hover {
    color: #fb0;
    border-bottom: none;
  }
  i {
    display: none;
  }
  @media (max-width: 840px) {
    header {
      flex-direction: column;
      align-items: flex-end;
      padding: 2em;
      line-height: 1em;
    }
    div {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    nav {
      display: block;
      width: 100%;
      text-align: center;
    }
    i {
      display: block;
      font-size: 2em;
    }
  }
</style>
