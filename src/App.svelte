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

  <section>
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

  <section>
    <Book />
  </section>

  <section>
    <Gallery />
  </section>

  <!-- <section>
    <article>
      <Events />
    </article>
  </section> -->

  <section>
    <Contact />
  </section>
</main>
<Footer />
