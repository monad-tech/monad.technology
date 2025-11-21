<script>
  let email = '';
  let message = '';
  let subject = 'Inquiry from Website';

  function handleSubmit(event) {
    event.preventDefault();
    const body = `From: ${email}\n\nMessage:\n${message}`;
    window.location.href = `mailto:contact.dpbf4@aleeas.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
  }
</script>

<svelte:head>
  <title>Monad Technologies LLC</title>
  <meta name="description" content="Consulting services for software development in distributed systems and cryptography protocols." />
</svelte:head>

<main>
  <section class="hero">
    <div class="container">
      <h1>Monad Technologies LLC</h1>
      <p class="tagline">Architecting the Future of Distributed Systems</p>
    </div>
  </section>

  <section class="about">
    <div class="container">
      <h2>About Us</h2>
      <p>
        Monad is a specialized consulting firm dedicated to advancing the frontiers of software development.
        We focus on <strong>distributed systems</strong> and <strong>cryptography protocols</strong>, helping organizations build secure, scalable, and resilient infrastructure.
      </p>
      <p>
        Our expertise bridges the gap between theoretical research and practical implementation, ensuring your systems are not only robust but also future-proof.
      </p>
    </div>
  </section>

  <section class="contact">
    <div class="container">
      <h2>Contact Us</h2>
      <p>Interested in working with us? Get in touch.</p>
      
      <form onsubmit={handleSubmit} class="contact-form">
        <div class="form-group">
          <label for="email">Your Email</label>
          <input type="email" id="email" bind:value={email} placeholder="name@example.com" required />
        </div>
        
        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" bind:value={message} rows="5" placeholder="How can we help you?" required></textarea>
        </div>

        <button type="submit">Send Message</button>
      </form>
    </div>
  </section>
</main>

<footer>
  <div class="container">
    <p>&copy; {new Date().getFullYear()} Monad Technologies LLC. All rights reserved.</p>
    <p class="social-links">
      <a href="https://github.com/monad-tech" target="_blank" rel="noopener noreferrer">GitHub</a>
    </p>
  </div>
</footer>

<style>
  .hero {
    padding: 8rem 0 4rem;
    text-align: center;
  }

  .tagline {
    font-size: 1.5rem;
    color: #888;
    margin-top: 1rem;
  }

  .about {
    background: var(--card-bg);
    padding: 4rem 0;
    margin: 2rem 0;
  }

  .about p {
    font-size: 1.1rem;
    max-width: 800px;
    margin-bottom: 1.5rem;
  }

  .contact {
    padding: 4rem 0;
  }

  .contact-form {
    max-width: 600px;
    margin-top: 2rem;
    background: var(--card-bg);
    padding: 2rem;
    border-radius: 12px;
    border: 1px solid #333;
  }

  .form-group {
    margin-bottom: 1.5rem;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
    color: #ccc;
  }

  .social-links {
    margin-top: 1rem;
  }
</style>
