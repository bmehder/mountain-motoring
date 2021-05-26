<script>
  import { onMount } from 'svelte'
  import Header from './Header.svelte'
  import Hero from './Hero.svelte'
  import About from './About.svelte'
  import Summary from './Summary.svelte'
  import Summary2 from './Summary2.svelte'
  import Image from './Image.svelte'
  import Image2 from './Image2.svelte'
  import Book from './Book.svelte'
  import Gallery from './Gallery.svelte'
  import Events from './Events.svelte'
  import Contact from './Contact.svelte'
  import Footer from './Footer.svelte'

  let input
  let value
  let isPublic = true

  const handleEnter = e => {
    e.key === 'Enter' && !isPublic && login()
  }
  const login = e => value === '123' && (isPublic = !isPublic)

  onMount(() => input?.focus())
</script>

{#if isPublic}
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
      <article id="book">
        <Book />
      </article>
    </section>

    <section id="contact">
      <Contact
        endpoint="https://getform.io/f/0615fe82-acf6-4e9b-8ba3-902a0309da6d"
        thankYou="Thank you for submitting your message. We will get back to you as soon as possible."
      />
    </section>
  </main>
  <Footer />
{:else}
  <aside
    style="display:flex;flex-direction:column;justify-content:center;align-items:center;max-width:400px;min-height:100vh;margin:auto;background:#154e1c;"
  >
    <input
      bind:this={input}
      bind:value
      type="text"
      placeholder="Enter password"
    />
    <a href="/" class="btn" on:click|preventDefault={login}>Login</a>
  </aside>
{/if}

<svelte:window on:keydown={handleEnter} />
