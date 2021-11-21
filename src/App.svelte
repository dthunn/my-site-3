<script>
  import * as animateScroll from 'svelte-scrollto';
  import IntersectionObserver from 'svelte-intersection-observer';

  import Header from './components/Header.svelte';
  import Hero from './components/Hero.svelte';
  import About from './components/About.svelte';
  import Skills from './components/Skills.svelte';
  import Contact from './components/Contact.svelte';
  import Footer from './components/Footer.svelte';

  let element;
  let intersecting;

  // animateScroll.setGlobalOptions({
  //   offset: -200,
  //   duration: 700,
  // });
</script>

<IntersectionObserver {element} bind:intersecting>
  <Header isIntersecting={intersecting} />
  <main>
    <Hero headerIsIntersecting={intersecting} />
    <About />
    <div bind:this={element}>
      <Skills />
      <Contact />
    </div>
  </main>
  <Footer />
</IntersectionObserver>

<style>
</style>
