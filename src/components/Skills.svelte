<script>
  import IntersectionObserver from 'svelte-intersection-observer'

  import MongoIcon from '../../public/img/mongo.svg'
  import PostgresIcon from '../../public/img/postgres.svg'
  import TSIcon from '../../public/img/typescript.svg'
  import AWSIcon from '../../public/img/aws.svg'
  import AzureIcon from '../../public/img/azure.svg'
  import GQLIcon from '../../public/img/gql.svg'
  import JavaIcon from '../../public/img/java.svg'
  import PythonIcon from 'devicon/icons/python/python-original.svg'
  import KubernetesIcon from 'simple-icons/icons/kubernetes.svg'
  import RedisIcon from 'simple-icons/icons/redis.svg'
  import ExpressIcon from 'simple-icons/icons/express.svg'
  import SpringBootIcon from 'simple-icons/icons/springboot.svg'
  import ReduxIcon from 'simple-icons/icons/redux.svg'
  import ClaudeIcon from 'simple-icons/icons/claude.svg'
  import ArgoIcon from 'simple-icons/icons/argo.svg'
  import MCPIcon from 'simple-icons/icons/modelcontextprotocol.svg'
  import HTML5Icon from 'simple-icons/icons/html5.svg'
  import CSS3Icon from 'simple-icons/icons/css.svg'
  import JSIcon from 'simple-icons/icons/javascript.svg'
  import NodeIcon from 'simple-icons/icons/nodedotjs.svg'
  import GithubIcon from 'simple-icons/icons/github.svg'
  import ReactIcon from 'simple-icons/icons/react.svg'
  import AngularIcon from 'simple-icons/icons/angular.svg'
  import DockerIcon from 'simple-icons/icons/docker.svg'

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
        <div class="skills-icon html" data-tooltip="HTML5">
          {@html HTML5Icon}
        </div>
        <div class="skills-icon css" data-tooltip="CSS3">
          {@html CSS3Icon}
        </div>
        <div class="skills-icon js" data-tooltip="JavaScript">
          {@html JSIcon}
        </div>
        <div class="skills-icon node" data-tooltip="Node.js">
          {@html NodeIcon}
        </div>
        <div class="skills-icon ts" data-tooltip="TypeScript">
          {@html TSIcon}
        </div>
        <div class="skills-icon github" data-tooltip="GitHub">
          {@html GithubIcon}
        </div>
        <div class="skills-icon react" data-tooltip="React">
          {@html ReactIcon}
        </div>
        <div class="skills-icon angular" data-tooltip="Angular">
          {@html AngularIcon}
        </div>
        <div class="skills-icon java" data-tooltip="Java">
          {@html JavaIcon}
        </div>
        <div class="skills-icon postgres" data-tooltip="PostgreSQL">
          {@html PostgresIcon}
        </div>
        <div class="skills-icon docker" data-tooltip="Docker">
          {@html DockerIcon}
        </div>
        <div class="skills-icon aws" data-tooltip="AWS">
          {@html AWSIcon}
        </div>
        <div class="skills-icon azure" data-tooltip="Azure">
          {@html AzureIcon}
        </div>
        <div class="skills-icon mongo" data-tooltip="MongoDB">
          {@html MongoIcon}
        </div>
        <div class="skills-icon graphql" data-tooltip="GraphQL">
          {@html GQLIcon}
        </div>
        <div class="skills-icon python" data-tooltip="Python">
          {@html PythonIcon}
        </div>
        <div class="skills-icon kubernetes" data-tooltip="Kubernetes">
          {@html KubernetesIcon}
        </div>
        <div class="skills-icon redis" data-tooltip="Redis">
          {@html RedisIcon}
        </div>
        <div class="skills-icon express" data-tooltip="Express">
          {@html ExpressIcon}
        </div>
        <div class="skills-icon springboot" data-tooltip="Spring Boot">
          {@html SpringBootIcon}
        </div>
        <div class="skills-icon redux" data-tooltip="Redux">
          {@html ReduxIcon}
        </div>
        <div class="skills-icon claude" data-tooltip="Claude">
          {@html ClaudeIcon}
        </div>
        <div class="skills-icon argo" data-tooltip="Argo Workflows">
          {@html ArgoIcon}
        </div>
        <div class="skills-icon mcp" data-tooltip="MCP">
          {@html MCPIcon}
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
    grid-template-columns: repeat(8, 1fr);
    justify-items: center;
    width: 860px;
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
  .skills-icons > *:nth-child(19) {
    transition-delay: 0.83s;
  }
  .skills-icons > *:nth-child(20) {
    transition-delay: 0.865s;
  }
  .skills-icons > *:nth-child(21) {
    transition-delay: 0.9s;
  }
  .skills-icons > *:nth-child(22) {
    transition-delay: 0.935s;
  }
  .skills-icons > *:nth-child(23) {
    transition-delay: 0.97s;
  }
  .skills-icons > *:nth-child(24) {
    transition-delay: 1.005s;
  }

  [data-tooltip] {
    position: relative;
  }

  [data-tooltip]::after {
    content: attr(data-tooltip);
    position: absolute;
    bottom: calc(100% + 1rem);
    left: 50%;
    transform: translateX(-50%) translateY(0.4rem);
    background-color: var(--color-white);
    color: var(--color-primary);
    font-size: 1.2rem;
    font-weight: 600;
    letter-spacing: 0.3px;
    padding: 0.4rem 1rem;
    border-radius: 4px;
    white-space: nowrap;
    box-shadow: 0 0.4rem 1rem rgba(0, 0, 0, 0.25);
    opacity: 0;
    pointer-events: none;
    transition:
      opacity 0.2s ease-out,
      transform 0.2s ease-out;
    z-index: 10;
  }

  [data-tooltip]:hover::after {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
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

  .skills-icon.html {
    fill: var(--color-secondary);
  }

  .skills-icon.css {
    fill: var(--color-primary-light);
  }

  .skills-icon.js {
    fill: var(--color-yellow);
  }

  .skills-icon.node {
    fill: var(--color-green);
  }

  .skills-icon.angular {
    fill: var(--color-red);
  }

  .skills-icon.github {
    fill: var(--color-white);
  }

  .skills-icon.react {
    fill: var(--color-primary-light);
  }

  .skills-icon.docker {
    fill: var(--color-primary-light);
  }

  .skills-icon.aws {
    fill: var(--color-secondary);
  }

  .skills-icon.kubernetes {
    fill: var(--color-white);
  }

  .skills-icon.redis {
    fill: var(--color-red);
  }

  .skills-icon.express {
    fill: var(--color-white);
  }

  .skills-icon.springboot {
    fill: var(--color-green);
  }

  .skills-icon.redux {
    fill: var(--color-pink);
  }

  .skills-icon.claude {
    fill: var(--color-secondary);
  }

  .skills-icon.argo {
    fill: #ef7b4d;
  }

  .skills-icon.mcp {
    fill: var(--color-white);
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
