<script>
  import IntersectionObserver from 'svelte-intersection-observer'

  import RustIcon from '../../public/img/rust.svg'
  import MongoIcon from '../../public/img/mongo.svg'
  import PostgresIcon from '../../public/img/postgres.svg'
  import TSIcon from '../../public/img/typescript.svg'
  import AWSIcon from '../../public/img/aws.svg'
  import AzureIcon from '../../public/img/azure.svg'
  import DOIcon from '../../public/img/digitalocean.svg'
  import GQLIcon from '../../public/img/gql.svg'
  import JestIcon from '../../public/img/jest.svg'
  import FigmaIcon from '../../public/img/figma.svg'
  import NetlifyIcon from '../../public/img/netlify.svg'
  import SvelteIcon from '../../public/img/svelte.svg'
  import JavaIcon from '../../public/img/java.svg'

  let element
  let intersecting = false
</script>

<IntersectionObserver {element} bind:intersecting once>
  <section class="skills">
    <div
      class="skills-container"
      bind:this={element}
      class:in-view={intersecting}
    >
      <h2 class="skills-header">Main Tech and Tools</h2>
      <div class="skills-icons">
        <ion-icon name="logo-html5" class="html" />
        <ion-icon name="logo-css3" class="skills-icon css" />
        <ion-icon name="logo-sass" class="skills-icon sass" />
        <ion-icon name="logo-javascript" class="skills-icon js" />
        <ion-icon name="logo-nodejs" class="skills-icon node" />
        <div class="skills-icon postgres">
          {@html TSIcon}
        </div>
        <ion-icon name="logo-github" class="skills-icon github" />
        <ion-icon name="logo-react" class="skills-icon react" />
        <ion-icon name="logo-angular" class="skills-icon npm" />
        <div class=" skills-icon mongo">
          {@html JavaIcon}
        </div>
        <div class="skills-icon postgres">
          {@html PostgresIcon}
        </div>
        <div class="skills-icon rust">
          {@html RustIcon}
        </div>
        <ion-icon name="logo-docker" class="skills-icon docker" />
        <div class="skills-icon aws">
          {@html AWSIcon}
        </div>
        <div class="skills-icon azure">
          {@html AzureIcon}
        </div>
        <div class="skills-icon figma">
          {@html FigmaIcon}
        </div>
        <div class="skills-icon figma">
          {@html MongoIcon}
        </div>
        <div class="skills-icon graphql">
          {@html GQLIcon}
        </div>
      </div>
    </div>
  </section>
</IntersectionObserver>

<style>
  .skills-container {
    opacity: 0;
    transform: translateY(8rem);
    transition: all 0.8s ease-in-out;
  }

  .in-view {
    opacity: 1;
    transform: translateY(0);
  }

  .skills {
    background-color: var(--color-primary);
  }

  .skills-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 10rem 4.8rem;
  }

  .skills-header {
    color: var(--color-white);
    text-align: center;
    font-size: 3rem;
    font-weight: 400;
    margin-bottom: 5rem;
  }

  .skills-icons {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    justify-items: center;
    width: 700px;
    margin: 0 auto;
    row-gap: 2rem;
  }

  .in-view .skills-icons > * {
    opacity: 1;
    transform: translateY(0);
  }

  .skills-icons > *:nth-child(1) {
    transition-delay: 0.2s;
  }
  .skills-icons > *:nth-child(2) {
    transition-delay: 0.235s;
  }
  .skills-icons > *:nth-child(3) {
    transition-delay: 0.27s;
  }
  .skills-icons > *:nth-child(4) {
    transition-delay: 0.305s;
  }
  .skills-icons > *:nth-child(5) {
    transition-delay: 0.34s;
  }
  .skills-icons > *:nth-child(6) {
    transition-delay: 0.375s;
  }
  .skills-icons > *:nth-child(7) {
    transition-delay: 0.41s;
  }
  .skills-icons > *:nth-child(8) {
    transition-delay: 0.445s;
  }
  .skills-icons > *:nth-child(9) {
    transition-delay: 0.48s;
  }
  .skills-icons > *:nth-child(10) {
    transition-delay: 0.515s;
  }
  .skills-icons > *:nth-child(11) {
    transition-delay: 0.55s;
  }
  .skills-icons > *:nth-child(12) {
    transition-delay: 0.585s;
  }
  .skills-icons > *:nth-child(13) {
    transition-delay: 0.62s;
  }
  .skills-icons > *:nth-child(14) {
    transition-delay: 0.655s;
  }
  .skills-icons > *:nth-child(15) {
    transition-delay: 0.69s;
  }
  .skills-icons > *:nth-child(16) {
    transition-delay: 0.725s;
  }
  .skills-icons > *:nth-child(17) {
    transition-delay: 0.76s;
  }
  .skills-icons > *:nth-child(18) {
    transition-delay: 0.795s;
  }

  .skills-icon {
    height: 5.2rem;
    width: 5.2rem;
    opacity: 0;
    transform: translateY(2rem);
    transition:
      opacity 0.5s ease-out,
      transform 0.35s ease-out;
  }

  .skills-icon:hover {
    transform: scale(1.15);
  }

  .skills-icon.css {
    color: var(--color-primary-light);
  }

  .skills-icon.sass {
    color: var(--color-pink);
  }

  .skills-icon.js {
    color: var(--color-yellow);
  }

  .skills-icon.node {
    color: var(--color-green);
  }

  .skills-icon.npm {
    color: var(--color-red);
  }

  .skills-icon.github {
    color: var(--color-white);
  }

  .skills-icon.react {
    color: var(--color-primary-light);
  }

  .skills-icon.docker {
    color: var(--color-primary-light);
  }

  .skills-icon.aws {
    fill: var(--color-secondary);
  }

  .html {
    height: 4.8rem;
    width: 4.8rem;
    color: var(--color-secondary);
    opacity: 0;
    transform: translateY(2rem);
    transition:
      opacity 0.5s ease-out,
      transform 0.35s ease-out;
  }

  .html:hover {
    transform: scale(1.15);
  }

  .rust {
    color: white;
    fill: var(--color-secondary);
  }

  .mongo {
    color: white;
    fill: var(--color-white);
  }

  .postgres {
    color: red;
  }

  @media (max-width: 59em) {
    .skills-icons {
      grid-template-columns: repeat(4, 1fr);
      width: 550px;
    }
  }

  @media (max-width: 39em) {
    .skills-header {
      font-size: 2.6rem;
    }

    .skills-icons {
      grid-template-columns: repeat(3, 1fr);
      width: 250px;
    }
  }

  @media (max-width: 38em) {
    .skills-header {
      font-size: 2rem;
    }

    .skills-icons {
      grid-template-columns: repeat(3, 1fr);
      width: 230px;
    }
  }

  @media (max-width: 35em) {
    .skills-header {
      font-size: 2rem;
    }

    .skills-icons {
      grid-template-columns: repeat(3, 1fr);
      width: 190px;
    }
  }
</style>
