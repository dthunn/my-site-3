<script>
  import IntersectionObserver from 'svelte-intersection-observer'

  let element
  let intersecting = false
</script>

<IntersectionObserver {element} bind:intersecting once>
  <section class="about" bind:this={element} class:in-view={intersecting}>
    <h2 class="about-header">A little about me...</h2>
    <p class="about-text">
      I'm a software engineer with 5+ years of experience building
      production-grade web applications, from frontend work
      to backend services and the cloud infrastructure that keeps it all
      running. My day-to-day toolkit spans JavaScript/TypeScript, React,
      Angular, Java, Node.js, Python, PostgreSQL, AWS, Docker/Kubernetes, among others.
    </p>
    <p class="about-text">
      Most recently, I worked on mission-critical ground operations software
      at Jeppesen ForeFlight, used by major U.S. and international airlines
      for flight planning and operational safety. That meant Angular on the
      frontend, Java microservices running on Kubernetes, ETL pipelines in
      Python and Argo Workflows, and GIS interfaces built with ArcGIS &mdash;
      plus contributing to the team's migration from Azure to AWS along the
      way.
    </p>
    <p class="about-text">
      Before that, I built automation tools inside PayPal's microservices
      architecture, shipped full-stack MERN applications, built frontend
      experiences with Next.js and Contentful, and worked on geospatial
      applications using React and CesiumJS.
    </p>
    <p class="about-text">
      I like problems that don't fit neatly into one layer of the stack, and
      I'm happiest owning something end-to-end &mdash; from the API design to
      the pixels the user actually sees. If you're looking for someone who can
      move fluidly between frontend, backend, and cloud, let's talk.
    </p>
  </section>
</IntersectionObserver>

<style>
  .about {
    max-width: 760px;
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
    margin-bottom: 3rem;
    font-weight: 400;
    color: var(--color-secondary-dark);
  }

  .about-text {
    text-align: left;
    font-size: 1.8rem;
    line-height: 1.7;
    font-weight: 500;
    margin-bottom: 2.4rem;
    letter-spacing: 0.5px;
  }

  .about-text:last-child {
    margin-bottom: 6rem;
  }

  @media (max-width: 59em) {
    .about-header {
      font-size: 3rem;
    }

    .about-text {
      font-size: 1.7rem;
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
      font-weight: 500;
    }
  }

  @media (max-width: 22em) {
    .about {
      padding: 0 4rem;
    }

    .about-header {
      font-size: 1.6rem;
    }

    .about-text {
      font-size: 1rem;
      font-weight: 500;
    }
  }
</style>
