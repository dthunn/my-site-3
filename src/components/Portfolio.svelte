<script>
  import IntersectionObserver from 'svelte-intersection-observer'

  let element
  let intersecting = false

  const projects = [
    {
      title: 'Omaha Place Finder',
      image: '/img/place-finder.png',
      description:
        'Natural-language place search for Omaha, NE. PostGIS handles the geography, pgvector handles the semantics, and an LLM ties the two together — results capped and rate-limited to prevent abuse.',
      url: 'https://ai-place-finder-one.vercel.app/',
    },
    {
      title: "What's in the Pantry",
      image: '/img/recipe-finder.png',
      description:
        'Describe a craving, what you have on hand, or a dietary constraint, and an LLM turns it into structured filters while pgvector finds the closest matches among 1,223 recipes. Ask the AI to adapt any recipe — vegan, gluten-free, halved — grounded in the original.',
      url: 'https://ai-recipe-helper-mu.vercel.app/',
    },
  ]
</script>

<IntersectionObserver {element} bind:intersecting once>
  <section class="portfolio">
    <div
      class="portfolio-container"
      bind:this={element}
      class:in-view={intersecting}
    >
      <h2 class="portfolio-header">Portfolio</h2>
      <p class="portfolio-intro">
        Most of my recent work lives behind closed doors at the companies
        I've worked for, so there's not much of it I can show here. Instead,
        here are a couple of things I've built recently to sharpen my AI
        skills.
      </p>
      <div class="portfolio-grid">
        {#each projects as project}
          <a
            class="portfolio-card"
            href={project.url}
            target="_blank"
            rel="noopener noreferrer"
          >
            <img
              class="portfolio-image"
              src={project.image}
              alt={`${project.title} screenshot`}
            />
            <div class="portfolio-card-body">
              <h3 class="portfolio-card-title">{project.title}</h3>
              <p class="portfolio-card-text">{project.description}</p>
              <span class="portfolio-link">View Project &rarr;</span>
            </div>
          </a>
        {/each}
      </div>
    </div>
  </section>
</IntersectionObserver>

<style>
  .portfolio-container {
    opacity: 0;
    transform: translateY(8rem);
    transition: all 0.8s ease-in-out;
  }

  .in-view {
    opacity: 1;
    transform: translateY(0);
  }

  .portfolio {
    background-color: var(--color-white);
  }

  .portfolio-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 10rem 4.8rem;
  }

  .portfolio-header {
    color: var(--color-secondary-dark);
    text-align: center;
    font-size: 3.2rem;
    font-weight: 400;
    margin-bottom: 2rem;
  }

  .portfolio-intro {
    max-width: 640px;
    margin: 0 auto 5rem;
    text-align: center;
    font-size: 1.6rem;
    line-height: 1.7;
    font-weight: 500;
    color: var(--color-primary);
    letter-spacing: 0.5px;
  }

  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 3rem;
  }

  .portfolio-card {
    display: flex;
    flex-direction: column;
    text-decoration: none;
    color: inherit;
    background-color: var(--color-primary);
    border-radius: 6px;
    overflow: hidden;
    box-shadow: 0px 0px 10px 2px rgba(0, 0, 0, 0.15);
    transition: all 0.3s ease-in-out;
  }

  .portfolio-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 1.2rem 2.4rem rgba(0, 0, 0, 0.25);
  }

  .portfolio-image {
    width: 100%;
    aspect-ratio: 16 / 10;
    object-fit: cover;
    object-position: top;
    display: block;
    border-bottom: 4px solid var(--color-secondary);
  }

  .portfolio-card-body {
    padding: 2.4rem 2.4rem 2.8rem;
  }

  .portfolio-card-title {
    font-size: 2.2rem;
    font-weight: 600;
    color: var(--color-white);
    margin-bottom: 1.2rem;
    letter-spacing: 0.5px;
  }

  .portfolio-card-text {
    font-size: 1.5rem;
    line-height: 1.6;
    font-weight: 500;
    color: var(--color-primary-light);
    margin-bottom: 1.6rem;
  }

  .portfolio-link {
    display: inline-block;
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--color-secondary);
    letter-spacing: 0.5px;
    transition: all 0.3s ease-in-out;
  }

  .portfolio-card:hover .portfolio-link {
    color: var(--color-secondary-dark);
  }

  @media (max-width: 59em) {
    .portfolio-grid {
      grid-template-columns: 1fr;
      max-width: 500px;
      margin: 0 auto;
    }
  }

  @media (max-width: 39em) {
    .portfolio-header {
      font-size: 2.6rem;
    }

    .portfolio-intro {
      font-size: 1.4rem;
    }

    .portfolio-card-title {
      font-size: 2rem;
    }

    .portfolio-card-text {
      font-size: 1.4rem;
    }
  }

  @media (max-width: 22em) {
    .portfolio-header {
      font-size: 2rem;
    }
  }
</style>
