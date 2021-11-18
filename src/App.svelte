<script>
  import IntersectionObserver from 'svelte-intersection-observer';

  import Header from './components/Header.svelte';
  import Hero from './components/Hero.svelte';
  import About from './components/About.svelte';
  import Skills from './components/Skills.svelte';

  let element;
  let intersecting;
</script>

<IntersectionObserver {element} bind:intersecting>
  <Header isIntersecting={intersecting} />
  <main>
    <Hero />
    <About />
    <div bind:this={element} />
    <Skills />
  </main>
</IntersectionObserver>

<style>
</style>
