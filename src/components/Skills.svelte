<script>
  import IntersectionObserver from 'svelte-intersection-observer';

  import RustIcon from '../../public/img/rust.svg';
  import MongoIcon from '../../public/img/mongo.svg';
  import PostgresIcon from '../../public/img/postgres.svg';
  import TSIcon from '../../public/img/typescript.svg';
  import AWSIcon from '../../public/img/aws.svg';
  import AzureIcon from '../../public/img/azure.svg';
  import DOIcon from '../../public/img/digitalocean.svg';
  import GQLIcon from '../../public/img/gql.svg';
  import JestIcon from '../../public/img/jest.svg';
  import FigmaIcon from '../../public/img/figma.svg';
  import NetlifyIcon from '../../public/img/netlify.svg';
  import SvelteIcon from '../../public/img/svelte.svg';

  let element;
  let intersecting;
</script>

<IntersectionObserver {element} bind:intersecting>
  <section id="skills" class="skills">
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
        <ion-icon name="logo-npm" class="skills-icon npm" />
        <ion-icon name="logo-github" class="skills-icon github" />
        <ion-icon name="logo-react" class="skills-icon react" />
        <ion-icon name="logo-docker" class="skills-icon docker" />
        <div class=" skills-icon mongo">
          {@html MongoIcon}
        </div>
        <div class="skills-icon jest">
          {@html JestIcon}
        </div>
      </div>
      <div class="skills-header-sub">Other Interests and Tools</div>
      <div class="skills-icons-other">
        <div class="skills-icon rust">
          {@html RustIcon}
        </div>
        <div class="skills-icon svelte">
          {@html SvelteIcon}
        </div>
        <div class="skills-icon graphql">
          {@html GQLIcon}
        </div>
        <div class="skills-icon figma">
          {@html FigmaIcon}
        </div>
        <div class="skills-icon aws">
          {@html AWSIcon}
        </div>
        <div class="skills-icon azure">
          {@html AzureIcon}
        </div>
        <div class="skills-icon postgres">
          {@html PostgresIcon}
        </div>
        <div class="skills-icon do">
          {@html DOIcon}
        </div>
        <div class="skills-icon netlify">
          {@html NetlifyIcon}
        </div>
        <ion-icon name="logo-angular" class="skills-icon angular" />
        <ion-icon name="logo-vercel" class="skills-icon vercel" />
        <ion-icon name="logo-python" class="skills-icon python" />
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
    margin-bottom: 10rem;
  }

  .skills-icon {
    height: 5.2rem;
    width: 5.2rem;
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

  .skills-icon.angular {
    color: var(--color-red);
  }

  .skills-icon.python {
    color: var(--color-yellow);
  }

  .skills-icon.vercel {
    color: var(--color-white);
  }

  .skills-icon.aws {
    fill: var(--color-secondary);
  }

  .skills-icon.do {
    fill: var(--color-primary-light);
  }

  .skills-header-sub {
    font-size: 2.2rem;
    text-align: center;
    color: var(--color-white);
    margin-bottom: 5rem;
    font-weight: 500;
  }

  .html {
    height: 4.8rem;
    width: 4.8rem;
    color: var(--color-secondary);
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

  .skills-icons-other {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    justify-items: center;
    width: 700px;
    margin: 0 auto;
    row-gap: 2.5rem;
  }

  @media (max-width: 59em) {
    .skills-icons {
      grid-template-columns: repeat(4, 1fr);
      width: 550px;
    }

    .skills-icons-other {
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

    .skills-icons-other {
      grid-template-columns: repeat(3, 1fr);
      width: 250px;
    }
  }
</style>
