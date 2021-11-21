<script>
  import IntersectionObserver from 'svelte-intersection-observer';

  let element;
  let intersecting;
</script>

<IntersectionObserver {element} bind:intersecting once>
  <section class="about" bind:this={element} class:in-view={intersecting}>
    <h2 class="about-header">A little about me...</h2>
    <p class="about-text">
      I am a graphic designer turned fullstack developer. After getting into
      graphic design because of a background in art, I never really felt it was
      meant for me. Then a friend of mine recommended I try coding a few years
      ago and I have never looked back. When not coding, I enjoy hiking with my
      dog, seeing live music, and being lazy and playing video games 😁.
    </p>
    <h3 class="role-header">
      Current Role - <span class="mern">MERN</span> Stack Developer at
      <span class="siros">Siros Technologies</span>
    </h3>
    <div class="role-list">
      <ul class="role-description">
        <li>Created frontend GUI in React.</li>
        <li>Auth with Node, Expess, JWT, and Mongo.</li>
        <li>Creating and saving user projects.</li>
        <li>Deployment with Docker and Azure.</li>
        <li>Testing with Jest and Supertest.</li>
        <li>Data visualization.</li>
      </ul>
    </div>
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
    font-weight: 500;
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
  }

  @media (max-width: 39em) {
    .about {
      padding: 0 4rem;
    }

    .about-header {
      font-size: 2.4rem;
    }

    .about-text {
      font-size: 1.4rem;
    }

    .role-header {
      font-size: 1.6rem;
      line-height: 1.6;
    }

    .role-description {
      font-size: 1.4rem;
    }
  }
</style>
