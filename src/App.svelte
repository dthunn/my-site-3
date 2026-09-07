<script>
  import IntersectionObserver from 'svelte-intersection-observer';

  import Header from './components/Header.svelte';
  import Hero from './components/Hero.svelte';
  import About from './components/About.svelte';
  import Portfolio from './components/Portfolio.svelte';
  import Skills from './components/Skills.svelte';
  import Contact from './components/Contact.svelte';
  import Footer from './components/Footer.svelte';

  let element;
  let intersecting = false;
</script>

<IntersectionObserver {element} bind:intersecting>
  <Header isIntersecting={intersecting} />
  <div id="home" />
  <main>
    <Hero headerIsIntersecting={intersecting} />
    <div id="about" />
    <About />
    <div id="portfolio" />
    <Portfolio />
    <div bind:this={element}>
      <div id="skills" />
      <Skills />
      <div id="contact" />
      <Contact />
    </div>
  </main>
  <Footer />
</IntersectionObserver>

<style>
</style>
