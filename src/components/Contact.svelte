<script>
  import IntersectionObserver from 'svelte-intersection-observer';

  let element;
  let intersecting;
  let formSubmitted = false;
  let formValues = {
    name: '',
    email: '',
    message: '',
  };

  const encode = (data) => {
    return Object.keys(data)
      .map(
        (key) => encodeURIComponent(key) + '=' + encodeURIComponent(data[key])
      )
      .join('&');
  };

  const handleSubmit = function (e) {
    e.preventDefault();

    fetch('/', {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: encode({ 'form-name': 'contact', ...formValues }),
    })
      .then(() => {
        alert('Success!');
        formSubmitted = true;
      })
      .catch((error) => alert(error));
  };
</script>

<IntersectionObserver {element} bind:intersecting>
  <section
    id="contact"
    class="contact"
    bind:this={element}
    class:in-view={intersecting}
  >
    <div class="contact-info">
      <h3 class="contact-info-header">A bit more info...</h3>
      <p class="contact-info-text">
        Check out my Github to see what projects I have worked on or take a peek
        at my resume below if your looking for a new developer. If you need to
        reach me, feel free to use the email below or just use the contact form!
      </p>
      <div class="contact-info-items">
        <div class="contact-info-item">
          <ion-icon name="logo-github" class="contact-icon" />
          <a href="https://github.com/dthunn" class="contact-link">My Github</a>
        </div>
        <div class="contact-info-item">
          <ion-icon name="mail-outline" class="contact-icon" />
          <h4>dylan@dthunn.com</h4>
        </div>
        <div class="contact-info-item">
          <ion-icon name="document-outline" class="contact-icon" />
          <a href="/img/dtresume.pdf" target="_blank" class="contact-link"
            >Resume</a
          >
        </div>
        <div class="contact-info-item">
          <ion-icon name="location-outline" class="contact-icon" />
          <h4>Denver, CO</h4>
        </div>
      </div>
    </div>
    <div class="contact-form">
      <h3 class="contact-form-header">Contact</h3>
      <form
        on:submit={handleSubmit}
        id="contact-form"
        class="contact-form-container"
      >
        <div>
          <input type="hidden" name="form-name" value="contact" />
          <label for="name" class="contact-form-label">Name</label>
          <input
            id="name"
            name="name"
            type="text"
            class="contact-form-input"
            bind:value={formValues.name}
          />
        </div>
        <div>
          <label for="email" class="contact-form-label">Email</label>
          <input
            id="email"
            name="email"
            type="email"
            class="contact-form-input"
            bind:value={formValues.email}
            required
          />
        </div>
        <div>
          <label for="message" class="contact-form-label">Message</label>
          <textarea
            name="message"
            id="message"
            cols="30"
            rows="6"
            class="contact-form-input"
            bind:value={formValues.message}
            required
          />
        </div>
        <button class="contact-form-btn" type="submit">Submit</button>
      </form>
    </div>
  </section>
</IntersectionObserver>

<style>
  .contact {
    margin: 12rem auto;
    max-width: 1000px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
    padding: 0 4.8rem;
    transform: translateY(8rem);
    opacity: 0;
    transition: all 0.8s ease-in-out;
  }

  .contact.in-view {
    opacity: 1;
    transform: translateY(0);
  }

  .contact-info {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .contact-info-header {
    padding-top: 1.6rem;
    font-size: 3rem;
    color: var(--color-primary);
    margin-bottom: 1rem;
    font-weight: 400;
  }

  .contact-info-text {
    font-size: 2rem;
    line-height: 1.6;
    font-weight: 500;
    color: var(--color-primary);
    width: 98%;
    margin-bottom: 1.6rem;
    letter-spacing: 1px;
  }

  .contact-info-item {
    display: flex;
    align-items: center;
    font-size: 2rem;
    font-weight: 600;
    color: var(--color-primary);
    margin-bottom: 0.8rem;
  }

  .contact-icon {
    font-size: 2.5rem;
    margin-right: 3rem;
    color: var(--color-secondary);
  }

  .contact-link {
    text-decoration: none;
    color: inherit;
  }

  .contact-form {
    border: 4px solid var(--color-primary);
    color: var(--color-secondary);
    background-color: var(--color-primary);
    padding: 1.6rem 0 2rem 0;
    box-shadow: 0px 0px 10px 2px rgba(0, 0, 0, 0.2);
  }

  .contact-form-label {
    display: block;
    font-size: 1.6rem;
    margin-bottom: 0.75rem;
  }

  .contact-form-container {
    padding: 0 3rem;
  }

  .contact-form-header {
    font-size: 3rem;
    padding: 0 3rem;
    background-color: var(--color-primary);
    margin-bottom: 1rem;
  }

  .contact-form-input {
    display: inline-block;
    width: 100%;
    margin-bottom: 0.5rem;
    padding: 0.5rem 1rem;
    border-radius: 3px;
    border: none;
    color: var(--color-primary);
    font-weight: 500;
    font-size: 2rem;
  }

  .contact-form-btn {
    display: inline-block;
    width: 100%;
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 3px;
    background-color: var(--color-secondary);
    font-size: 2rem;
    margin-top: 1rem;
    cursor: pointer;
    transition: all 0.3s ease-in-out;
  }

  .contact-form-btn:hover {
    background-color: var(--color-secondary-dark);
    color: var(--color-white);
  }

  @media (max-width: 59em) {
    .contact {
      display: block;
      max-width: 580px;
    }

    .contact-info-header {
      text-align: center;
    }

    .contact-info-text {
      text-align: center;
    }

    .contact-info-items {
      margin: 0 auto;
      margin-bottom: 4rem;
      display: grid;
      grid-template-columns: repeat(2, 1fr);
    }

    @media (max-width: 39em) {
      .contact-info-header {
        font-size: 2.4rem;
      }

      .contact-info-text {
        font-size: 1.4rem;
      }

      .contact-info-item {
        font-size: 1.6rem;
      }

      .contact-icon {
        font-size: 2rem;
        margin-right: 2rem;
        color: var(--color-secondary);
      }
    }
  }
</style>
