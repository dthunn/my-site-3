<script>
  import { scrollto } from 'svelte-scrollto';

  export let isIntersecting;
  let navOpen = false;

  const toggleNav = function () {
    navOpen = !navOpen;
  };

  const toggleNavAncor = function () {
    navOpen = false;
  };

  const toggleNavUl = function (e) {
    // if (e.target.classList.contains('main-nav-link')) {
    //   console.log(true);
    //   navOpen = false;
    // }
    navOpen = false;
  };
</script>

<header
  id="home"
  class="header"
  class:nav-open={navOpen}
  class:sticky={isIntersecting}
>
  <nav class="main-nav" on:click={toggleNavUl}>
    <div>
      <a href="home">
        {#if !isIntersecting}
          <img
            class="logo"
            alt="Dylan Thunn Logo"
            src="/img/logo.png"
            use:scrollto={'#home'}
          />
        {:else}
          <img
            class="logo"
            alt="Dylan Thunn Logo"
            src="/img/logo-dark.png"
            use:scrollto={'#home'}
          />
        {/if}
      </a>
    </div>
    <ul class="main-nav-list" on:click={toggleNavUl}>
      <li class="main-nav-link">
        <a class="main-nav-link" href="#about" use:scrollto={'#about'}>About</a>
      </li>
      <li class="main-nav-link">
        <a class="main-nav-link" href="#skills" use:scrollto={'#skills'}
          >Skills</a
        >
      </li>
      <li class="main-nav-link">
        <a
          class="main-nav-link nav-cta"
          href="#contact"
          use:scrollto={'#contact'}>Contact</a
        >
      </li>
    </ul>
  </nav>

  <a href={'#'}>
    {#if !isIntersecting}
      <img class="logo-mobile" alt="Dylan Thunn Logo" src="/img/logo.png" />
    {:else}
      <img
        class="logo-mobile"
        alt="Dylan Thunn Logo"
        src="/img/logo-dark.png"
      />
    {/if}
  </a>

  <button class="btn-mobile-nav" on:click={toggleNav}>
    {#if !navOpen}
      <ion-icon
        class="icon-mobile-nav"
        name="menu-outline"
        class:intersecting={isIntersecting}
      />
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
    /* position: absolute; */
    top: 0;
    left: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: transparent;

    /* Because we want header to be sticky later */
    height: 8rem;
    padding: 0 4.8rem;
    z-index: 1000;
    width: 100%;
    color: white;
    position: relative;
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
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
    font-weight: 600;
    font-size: 1.8rem;
    transition: all 0.3s;
    letter-spacing: 1px;
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

  .intersecting {
    color: var(--color-primary);
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
    -webkit-transform: translate3d(0, 0, 0);
    -moz-transform: translate3d(0, 0, 0);
    -ms-transform: translate3d(0, 0, 0);
    -o-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
  }

  /* .header.sticky {
    margin-top: 8rem;
  } */

  .header.sticky .main-nav-link:link,
  .header.sticky .main-nav-link:visited {
    color: var(--color-primary);
  }

  .header.sticky .main-nav-link:link:hover,
  .header.sticky .main-nav-link:visited:hover {
    color: var(--color-secondary);
  }

  .header.sticky .main-nav-link.nav-cta:link,
  .header.sticky .main-nav-link.nav-cta:visited {
    color: var(--color-white);
  }

  .header.sticky .main-nav-link.nav-cta:link:hover,
  .header.sticky .main-nav-link.nav-cta:visited:hover {
    color: var(--color-white);
  }

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
      opacity: 0;
      /* pointer-events: none; */
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
      z-index: 9999;
    }

    .main-nav-link:hover,
    .main-nav-link:active {
      color: #cf711f;
    }
  }
</style>
