<script></script>

<footer class="footer">
  <div class="footer-text">
    Copyright © Dylan Thunn {new Date().getFullYear()}
  </div>
</footer>

<style>
  footer {
    background-color: var(--color-primary);
  }

  .footer {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 12rem;
  }

  .footer-text {
    color: var(--color-white);
    font-size: 2rem;
    font-weight: 500;
  }

  @media (max-width: 39em) {
    .footer-text {
      font-size: 1.4rem;
    }
  }
</style>
