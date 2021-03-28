<script>
  import Header from "./Header.svelte";
  import Hero from "./Hero.svelte";
  import About from "./About.svelte";
  import Summary from "./Summary.svelte";
  import Summary2 from "./Summary2.svelte";
  import Image from "./Image.svelte";
  import Image2 from "./Image2.svelte";
  import Book from "./Book.svelte";
  import Gallery from "./Gallery.svelte";
  import Events from "./Events.svelte";
  import Contact from "./Contact.svelte";
  import Footer from "./Footer.svelte";
</script>

<Header />
<main>
  <section>
    <Hero />
  </section>

  <section id="about">
    <About />
  </section>

  <section>
    <Summary />
    <Image />
  </section>

  <section>
    <Image2 />
    <Summary2 />
  </section>

  <section id="events">
    <Events />
  </section>

  <section id="gallery">
    <Gallery />
  </section>

  <section>
    <article>
      <Book />
    </article>
  </section>

  <section id="contact">
    <Contact />
  </section>
</main>
<Footer />

<svelte:head>
  <title>Mountain Motoring - Sept 10-12, 2021 - Highlands, NC</title>
  <meta
    name="description"
    content="Come drive at the Mountain Motoring in Highlands, NC, share your interest in cars, and help us support our local charities."
  />
</svelte:head>
