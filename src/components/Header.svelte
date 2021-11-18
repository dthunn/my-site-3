<script>
  import { scrollto } from 'svelte-scrollto';

  let navOpen = false;
  export let isIntersecting;

  const toggleNav = function () {
    navOpen = !navOpen;
  };

  const toggleNavAncor = function () {
    navOpen = false;
  };
</script>

<header
  class="header nav-open"
  class:nav-open={navOpen}
  class:sticky={isIntersecting}
>
  <nav class="main-nav">
    <div>
      <a href={'#'}>
        {#if !isIntersecting}
          <img class="logo" alt="Dylan Thunn Logo" src="/img/logo.png" />
        {:else}
          <img class="logo" alt="Dylan Thunn Logo" src="/img/logo-dark.png" />
        {/if}
      </a>
    </div>
    <ul class="main-nav-list">
      <li>
        <a
          class="main-nav-link"
          href="#about"
          on:click={toggleNavAncor}
          use:scrollto={'#about'}>About</a
        >
      </li>
      <li>
        <a class="main-nav-link" on:click={toggleNavAncor} href={'#'}>Skills</a>
      </li>
      <li>
        <a class="main-nav-link nav-cta" on:click={toggleNavAncor} href={'#'}
          >Contact</a
        >
      </li>
    </ul>
  </nav>

  <a href={'#'}>
    <img class="logo-mobile" alt="Dylan Thunn Logo" src="/img/logo.png" />
  </a>

  <button class="btn-mobile-nav" on:click={toggleNav}>
    {#if !navOpen}
      <ion-icon class="icon-mobile-nav" name="menu-outline" />
    {:else}
      <ion-icon class="icon-mobile-nav close" name="close-outline" />
    {/if}
  </button>
</header>

<style>
  /**************************/
  /* HEADER */
  /**************************/

  .header {
    position: absolute;
    top: 0;
    left: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;

    /* Because we want header to be sticky later */
    height: 9.6rem;
    padding: 0 4.8rem;
    z-index: 1000;
    width: 100%;
    color: white;
    /* position: relative; */
  }

  .logo {
    height: 6rem;
  }

  .logo-mobile {
    height: 6rem;
    display: none;
  }

  /**************************/
  /* NAVIGATION */
  /**************************/

  .main-nav {
    display: flex;
    justify-content: space-between;
    width: 1200px;
    margin: 0 auto;
  }

  .main-nav-list {
    list-style: none;
    display: flex;
    align-items: center;
    gap: 4.8rem;
  }

  .main-nav-link:link,
  .main-nav-link:visited {
    display: inline-block;
    text-decoration: none;
    color: white;
    font-weight: 500;
    font-size: 1.8rem;
    transition: all 0.3s;
  }

  .main-nav-link:hover,
  .main-nav-link:active {
    color: #cf711f;
  }

  .main-nav-link.nav-cta:link,
  .main-nav-link.nav-cta:visited {
    padding: 1.2rem 2.4rem;
    border-radius: 22px;
    color: #fff;
    background-color: #e67e22;
  }

  .main-nav-link.nav-cta:hover,
  .main-nav-link.nav-cta:active {
    background-color: var(--color-secondary-dark);
  }

  /* MOBILE */
  .btn-mobile-nav {
    border: none;
    background: none;
    cursor: pointer;

    display: none;
  }

  .icon-mobile-nav {
    height: 4.8rem;
    width: 4.8rem;
    color: var(--color-white);
    transition: all 0.3s ease-in-out;
  }

  .icon-mobile-nav:hover {
    color: var(--color-secondary);
  }

  .icon-mobile-nav.close {
    color: var(--color-primary);
  }

  .icon-mobile-nav.close:hover {
    color: var(--color-secondary);
  }

  /* STICKY NAVIGATION */
  .header.sticky {
    position: fixed;
    top: 0;
    bottom: 0;
    width: 100%;
    height: 8rem;
    padding-top: 0;
    padding-bottom: 0;
    background-color: var(--color-white);
    z-index: 999;
    box-shadow: 0 1.2rem 3.2rem rgba(0, 0, 0, 0.2);
  }

  .header.sticky .main-nav-link {
    color: var(--color-primary);
  }

  /* .sticky .section-hero {
    margin-top: 9.6rem;
  } */

  @media (max-width: 59em) {
    /* MOBILE NAVIGATION */
    .btn-mobile-nav {
      display: block;
      z-index: 9999;
    }

    .main-nav {
      background-color: rgba(255, 255, 255, 0.9);
      -webkit-backdrop-filter: blur(5px);
      backdrop-filter: blur(10px);
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100vh;
      transform: translateX(100%);

      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.3s ease-in;

      /* Hide navigation */
      /* Allows NO transitions at all */
      /* display: none; */

      /* 1) Hide it visually */
      opacity: 0;

      /* 2) Make it unaccessible to mouse and keyboard */
      pointer-events: none;

      /* 3) Hide it from screen readers */
      visibility: hidden;
    }

    .main-nav .logo {
      display: none;
    }

    .logo-mobile {
      display: block;
    }

    .nav-open .main-nav {
      opacity: 1;
      pointer-events: auto;
      visibility: visible;
      transform: translateX(0);
    }

    .main-nav-list {
      flex-direction: column;
      gap: 4.8rem;
    }

    .main-nav-link:link,
    .main-nav-link:visited {
      font-size: 3rem;
      color: var(--color-primary);
    }

    .main-nav-link:hover,
    .main-nav-link:active {
      color: #cf711f;
    }
  }
</style>
