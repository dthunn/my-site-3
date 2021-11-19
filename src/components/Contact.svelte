<script>
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
      body: encode({
        'form-name': e.target.getAttribute('name'),
        ...formValues,
      }),
    })
      .then(() => {
        alert('Success!');
        formSubmitted = true;
      })
      .catch((error) => alert(error));
  };

  $: {
    console.log(formSubmitted);
  }
</script>

<section class="contact">
  <div class="contact-info">
    <h3 class="contact-info-header">Some Info</h3>
    <div class="contact-info-item">
      <ion-icon name="location-outline" class="contact-icon" />
      <h4>Denver, CO</h4>
    </div>
    <div class="contact-info-item">
      <ion-icon name="mail-outline" class="contact-icon" />
      <h4>dylan@dthunn.com</h4>
    </div>
    <div class="contact-info-item">
      <ion-icon name="logo-github" class="contact-icon" />
      <a href="https://github.com/dthunn" class="contact-link">My Github</a>
    </div>
    <div class="contact-info-item">
      <ion-icon name="document-outline" class="contact-icon" />
      <a href="/img/dtresume.pdf" target="_blank" class="contact-link">Resume</a
      >
    </div>
  </div>
  <div class="contact-form">
    <h3 class="contact-form-header">Contact</h3>
    <form
      on:submit={handleSubmit}
      id="contact-form"
      name="contact"
      class="contact-form-container"
      method="POST"
      netlify
      data-netlify-recaptcha="true"
    >
      <div>
        <input type="hidden" name="form-name" value="contact" />
        <label for="name" class="contact-form-label">Name</label>
        <input
          id="name"
          name="name"
          type="text"
          class="contact-form-input"
          placeholder="Name"
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
          placeholder="Email"
          required
        />
      </div>
      <div>
        <label for="message" class="contact-form-label">Message</label>
        <textarea
          name="message"
          id="message"
          cols="30"
          rows="8"
          class="contact-form-input"
          placeholder="Message"
          required
        />
      </div>
      <button class="contact-form-btn" type="submit">Submit</button>
    </form>
  </div>
</section>

<style>
  .contact {
    margin: 12rem auto;
    max-width: 1000px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
    padding: 0 4.8rem;
  }

  .contact-info {
    border: 3px solid var(--color-primary);
    background-color: var(--color-primary);
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .contact-info-header {
    background-color: var(--color-secondary);
    padding: 1rem 3rem;
    font-size: 3rem;
    color: var(--color-primary);
  }

  .contact-info-item {
    padding: 2rem 3rem;
    display: flex;
    align-items: center;
    font-size: 2.2rem;
    font-weight: 600;
    color: var(--color-white);
  }

  .contact-icon {
    font-size: 3rem;
    margin-right: 3rem;
  }

  .contact-link {
    text-decoration: none;
    color: inherit;
  }

  .contact-form {
    border: 4px solid var(--color-primary);
    color: var(--color-secondary);
    background-color: var(--color-primary);
    padding: 2rem 0;
    box-shadow: 0px 0px 10px 2px rgba(0, 0, 0, 0.2);
  }

  .contact-form-label {
    display: block;
    font-size: 2rem;
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
  }
</style>
