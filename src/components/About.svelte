<script>
  import IntersectionObserver from 'svelte-intersection-observer'

  let element
  let intersecting
</script>

<IntersectionObserver {element} bind:intersecting once>
  <section class="about" bind:this={element} class:in-view={intersecting}>
    <h2 class="about-header">A little about me...</h2>
    <p class="about-text">
      As an adept software developer, I possess a talent for crafting
      sophisticated solutions to complex problems. With a solid command of
      various programming languages and frameworks, I have honed my expertise in
      translating abstract concepts into intuitive, user-focused applications.
      My proficiency extends across various domains, including front-end
      development, back-end engineering, database management, and the entirety
      of the software development lifecycle – from initial planning to
      deployment and beyond. Fueled by a passionate commitment to advancing
      technology, I am dedicated to spearheading innovations that redefine and
      elevate user experiences.
    </p>
  </section>
</IntersectionObserver>

<style>
  .about {
    max-width: 1000px;
    margin: 10rem auto;
    color: var(--color-primary);
    padding: 0 4.8rem;
    transition: all 0.8s ease-in-out;
    opacity: 0;
    transform: translateY(8rem);
  }

  .in-view {
    opacity: 1;
    transform: translateY(0);
  }

  .about-header {
    font-size: 3.2rem;
    text-align: center;
    margin-bottom: 3rem;
    font-weight: 400;
    color: var(--color-secondary-dark);
  }

  .about-text {
    text-align: center;
    font-size: 2rem;
    line-height: 1.6;
    font-weight: 600;
    margin-bottom: 6rem;
    letter-spacing: 1px;
  }

  .role-header {
    font-size: 2.4rem;
    text-align: center;
    font-weight: 600;
    margin-bottom: 3rem;
    letter-spacing: 1px;
  }

  .mern {
    color: var(--color-secondary-dark);
  }

  .role-list {
    display: flex;
    justify-content: center;
    font-weight: 600;
  }

  .role-description {
    margin: 0 auto;
    list-style: none;
    font-size: 2rem;
    font-weight: 600;
    white-space: nowrap;
    letter-spacing: 1px;
  }

  ul li {
    margin-bottom: 1rem;
  }

  ul li::before {
    content: '\2022';
    display: inline-block;
    color: var(--color-secondary-dark);
    font-weight: bold;
    margin-left: -1rem;
    width: 5rem;
  }

  @media (max-width: 59em) {
    .about-header {
      font-size: 3rem;
    }

    .about-text {
      font-size: 1.8rem;
    }

    .siros {
      display: block;
    }

    .role-header {
      font-size: 2rem;
      line-height: 1.6;
    }

    .role-description {
      font-size: 1.8rem;
    }

    ul li::before {
      width: 2rem;
    }
  }

  @media (max-width: 39em) {
    .about {
      padding: 0 4rem;
    }

    .siros {
      display: inline-block;
    }

    .about-header {
      font-size: 2.4rem;
    }

    .about-text {
      font-size: 1.4rem;
      font-weight: 600;
    }

    .role-header {
      font-size: 1.6rem;
      line-height: 1.6;
    }

    .role-description {
      font-size: 1.4rem;
    }
  }

  @media (max-width: 39em) {
    .about {
      padding: 0 4rem;
    }

    .siros {
      display: inline-block;
    }

    .about-header {
      font-size: 2.4rem;
    }

    .about-text {
      font-size: 1.4rem;
      font-weight: 600;
    }

    .role-header {
      font-size: 1.6rem;
      line-height: 1.6;
    }

    .role-description {
      font-size: 1.4rem;
      font-weight: 600;
      white-space: normal;
    }
  }

  @media (max-width: 22em) {
    .about {
      padding: 0 4rem;
    }

    .siros {
      display: inline-block;
    }

    .about-header {
      font-size: 1.6rem;
    }

    .about-text {
      font-size: 1rem;
      font-weight: 600;
    }

    .role-header {
      font-size: 1rem;
      line-height: 1.6;
    }

    .role-description {
      font-size: 1rem;
      font-weight: 600;
      white-space: nowrap;
    }
  }
</style>
