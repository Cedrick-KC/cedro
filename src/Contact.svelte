<script>
  let name = '';
  let email = '';
  let message = '';

  let isSending = false;
  let formMessage = '';
  let isError = false;

  async function handleSubmit(event) {
    event.preventDefault(); // Prevent the default form submission

    isSending = true;
    formMessage = '';
    isError = false;

    // A simple validation
    if (!name || !email || !message) {
      formMessage = 'Please fill out all fields.';
      isError = true;
      isSending = false;
      return;
    }

    try {
      const response = await fetch('/api/contact', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({ name, email, message })
      });

      if (response.ok) {
        formMessage = 'Message sent successfully!';
        isError = false;
        // Reset the form
        name = '';
        email = '';
        message = '';
      } else {
        const errorData = await response.json();
        formMessage = `Failed to send message: ${errorData.error || 'Server error'}`;
        isError = true;
      }
    } catch (error) {
      formMessage = 'An unexpected error occurred. Please try again later.';
      isError = true;
    } finally {
      isSending = false;
    }
  }
</script>

<section class="contact-section">
  <h2 class="section-title">Contact</h2>
  <form on:submit={handleSubmit} class="contact-form">
    <input bind:value={name} type="text" placeholder="Your Name" />
    <input bind:value={email} type="email" placeholder="Your Email" />
    <textarea bind:value={message} placeholder="Your Message"></textarea>
    <button type="submit" disabled={isSending}>
      {isSending ? 'Sending...' : 'Send Message'}
    </button>
  </form>
  
  {#if formMessage}
    <p class="status-message" class:error={isError}>
      {formMessage}
    </p>
  {/if}

  <div class="social-links">
    <a href="#" target="_blank">LinkedIn</a>
    <a href="https://github.com/Cedrick-KC" target="_blank">GitHub</a>
    <a href="https://dev.to/cedrique_dev?" target="_blank">DEV Community</a>
    <a href="#" target="_blank">cedrique000@gmail.com</a>
  </div>
</section>

<style>
  .contact-section {
    margin-top: 2rem;
  }
  .section-title {
    color: #58a6ff;
    border-bottom: 1px solid #333;
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
  }
  .contact-form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
  input, textarea, button {
    padding: 0.75rem;
    border-radius: 8px;
    border: 1px solid #30363d;
    background-color: #0d1117;
    color: #e6edf3;
  }
  button {
    background-color: #58a6ff;
    cursor: pointer;
    font-weight: bold;
    transition: background-color 0.2s ease;
  }
  button:hover:not(:disabled) {
    background-color: #79c0ff;
  }
  button:disabled {
    background-color: #30363d;
    cursor: not-allowed;
  }
  .status-message {
    margin-top: 1rem;
    text-align: center;
    padding: 0.5rem;
    border-radius: 4px;
    background-color: #21262d;
    color: #58a6ff;
  }
  .status-message.error {
    color: #ff7b72;
  }
  .social-links {
    margin-top: 2rem;
    text-align: center;
  }
  .social-links a {
    color: #58a6ff;
    text-decoration: none;
    margin: 0 1rem;
    font-weight: bold;
  }
</style>