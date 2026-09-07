<script>
  export let headerIsIntersecting

  function scrollToAbout() {
    document.querySelector('#about').scrollIntoView({ behavior: 'smooth' })
  }
</script>

<section id="#home" class="hero" class:in-view={headerIsIntersecting}>
  <div class="hero-container">
    <div class="hero-terminal-line">
      <span class="hero-prompt">visitor@dthunn.com</span><span
        class="hero-prompt-sep">:~$</span
      > whoami
    </div>
    <div class="hero-header-main">Dylan Thunn<span class="hero-cursor" /></div>
    <div class="hero-terminal-line hero-terminal-line-2">
      <span class="hero-prompt">visitor@dthunn.com</span><span
        class="hero-prompt-sep">:~$</span
      > cat role.txt
    </div>
    <div class="hero-header-sub">Software Engineer / Lifelong Learner</div>
    <div>
      <button class="hero-header-btn btn-scroll-to" on:click={scrollToAbout}>
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

  .hero-terminal-line {
    opacity: 0;
    font-size: 1.5rem;
    font-weight: 500;
    letter-spacing: 0.5px;
    color: var(--color-white);
    animation: fadeInUp 0.5s ease-out forwards;
  }

  .hero-terminal-line-2 {
    margin-top: -0.6rem;
    margin-bottom: 0.6rem;
    animation-delay: 1.1s;
  }

  .hero-prompt {
    color: var(--color-secondary);
  }

  .hero-prompt-sep {
    color: var(--color-secondary);
    margin-right: 0.6rem;
  }

  .hero-cursor {
    display: inline-block;
    width: 0.11em;
    height: 0.7em;
    margin-left: 0.2em;
    vertical-align: -0.06em;
    background-color: var(--color-secondary);
    animation: blink 1s step-end infinite;
  }

  .hero-header-main {
    padding-top: 4rem;
    font-size: 9.8rem;
    font-weight: 400;
    word-spacing: -20px;
    opacity: 0;
    animation-name: moveInLeft;
    animation-duration: 0.9s;
    animation-timing-function: ease-out;
    animation-delay: 0.4s;
    animation-fill-mode: forwards;
    margin-bottom: 1.6rem;
    /* letter-spacing: 1px; */
  }

  .hero-header-sub {
    font-size: 2rem;
    opacity: 0;
    animation: moveInRight 0.9s ease-out 1.5s forwards;
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
    transition: color 0.3s, transform 0.3s;
    letter-spacing: 1px;
    opacity: 0;
    animation: moveInBottom 0.9s ease-out 2.2s forwards;
    position: relative;
    letter-spacing: 1px;
  }

  .hero-header-btn:hover {
    color: var(--color-secondary-dark);
    transform: translateY(-2px);
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

  @keyframes fadeInUp {
    0% {
      opacity: 0;
      transform: translateY(1rem);
    }

    100% {
      opacity: 1;
      transform: translate(0);
    }
  }

  @keyframes blink {
    0%,
    100% {
      opacity: 1;
    }

    50% {
      opacity: 0;
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

    .hero-terminal-line {
      font-size: 1.4rem;
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

    .hero-terminal-line {
      font-size: 1.1rem;
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
