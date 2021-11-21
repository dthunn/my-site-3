<script>
  import { scrollto } from 'svelte-scrollto';

  export let headerIsIntersecting;
</script>

<section id="#home" class="hero" class:in-view={headerIsIntersecting}>
  <div class="hero-container">
    <div class="hero-header-main">Dylan Thunn</div>
    <div class="hero-header-sub">Fullstack Developer / Lifelong Learner</div>
    <div>
      <button class="hero-header-btn btn-scroll-to" use:scrollto={'#about'}>
        Learn more &DownArrow;
      </button>
    </div>
  </div>
</section>

<style>
  .hero {
    background-image: url(../../img/background.jpg);
    height: 95vh;
    background-size: cover;
    position: relative;
    padding: 0 4.8rem;
    color: var(--color-white);
    margin-top: -8rem;
  }

  .hero.in-view {
    margin-top: 0;
  }

  .hero-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100%;
    max-width: 1200px;
    margin: 0 auto;
  }

  .hero-header-main {
    padding-top: 4rem;
    font-size: 9.8rem;
    font-weight: 400;
    word-spacing: -20px;
    animation-name: moveInLeft;
    animation-duration: 1s;
    animation-timing-function: ease-out;
    margin-bottom: 1.6rem;
    /* letter-spacing: 1px; */
  }

  .hero-header-sub {
    font-size: 2rem;
    animation: moveInRight 1s ease-out;
    margin-bottom: 1.4rem;
    font-weight: 500;
    letter-spacing: 1px;
  }

  .hero-header-btn {
    font-size: 2rem;
    display: block;
    background: none;
    font-family: inherit;
    font-weight: 500;
    color: var(--color-secondary);
    border: none;
    border-bottom: 1px solid currentColor;
    padding-bottom: 2px;
    cursor: pointer;
    transition: all 0.3s;
    letter-spacing: 1px;
    animation: moveInBottom 1s ease-out;
    position: relative;
    letter-spacing: 1px;
  }

  .hero-header-btn:hover {
    color: var(--color-secondary-dark);
  }

  @keyframes moveInLeft {
    0% {
      opacity: 0;
      transform: translateX(-10rem);
    }

    80% {
      transform: translateX(1rem);
    }

    100% {
      opacity: 1;
      transform: translate(0);
    }
  }

  @keyframes moveInRight {
    0% {
      opacity: 0;
      transform: translateX(10rem);
    }

    80% {
      transform: translateX(-1rem);
    }

    100% {
      opacity: 1;
      transform: translate(0);
    }
  }

  @keyframes moveInBottom {
    0% {
      opacity: 0;
      transform: translateY(3rem);
    }

    100% {
      opacity: 1;
      transform: translate(0);
    }
  }

  @media (max-width: 59em) {
    .hero {
      height: 80vh;
      background-size: cover;
      background-position: top;
    }

    .hero-container {
      align-items: center;
    }

    .hero-header-main {
      padding-top: 0;
      font-size: 8em;
    }

    .hero-header-sub {
      font-size: 2rem;
    }

    .hero-header-btn {
      font-size: 2rem;
    }
  }

  @media (max-width: 39em) {
    .hero {
      height: 75vh;
      padding: 0 3rem;
    }

    .hero-header-main {
      font-size: 4rem;
      word-spacing: 1px;
    }

    .hero-header-sub {
      font-size: 1.4rem;
    }

    .hero-header-btn {
      font-size: 1.4rem;
    }
  }

  /* @media (max-width: 39em) {
    .hero-header-main {
      font-size: 4.6rem;
    }

    .hero-header-sub {
      font-size: 1.2rem;
    }

    .hero-header-btn {
      font-size: 1.2rem;
    }
  } */

  @media (max-width: 23em) {
    .hero-header-main {
      font-size: 4rem;
    }

    .hero-header-sub {
      font-size: 1rem;
    }

    .hero-header-btn {
      font-size: 1.2rem;
    }
  }

  @media (max-width: 20em) {
    .hero-header-main {
      font-size: 3.4rem;
      word-spacing: 1px;
    }

    .hero-header-sub {
      font-size: 0.8rem;
    }
  }
</style>
