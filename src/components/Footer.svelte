<script></script>

<footer class="footer">
  <div class="footer-text">
    © Dylan Thunn {new Date().getFullYear()}
  </div>
</footer>

<style>
  footer {
    background-color: var(--color-white);
  }

  .footer {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 12rem;
  }

  .footer-text {
    color: var(--color-primary);
    font-size: 2rem;
    font-weight: 500;
  }

  @media (max-width: 39em) {
    .footer-text {
      font-size: 1.4rem;
    }
  }
</style>
