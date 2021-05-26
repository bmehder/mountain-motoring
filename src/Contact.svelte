<script>
  let form

  let name
  let email
  let message
  let isFormSubmitted = false
  let error = false

  export let endpoint = ''
  export let thankYou = ''

  function submitForm(e) {
    const formData = new FormData()

    formData.append('name', name)
    formData.append('email', email)
    formData.append('message', message)

    fetch(endpoint, { method: 'POST', body: formData })
      .then(response => (isSubmitted = true))
      .catch(err => (error = err))

    form.reset()
  }
</script>

<div>
  <h3>Send Us A Message</h3>
  <form bind:this={form} on:submit|preventDefault={submitForm}>
    <input
      bind:value={name}
      placeholder="Enter your name..."
      type="text"
      name="name"
      required
    />
    <input
      bind:value={email}
      placeholder="Enter your email..."
      type="email"
      name="email"
      required
    />
    <textarea
      bind:value={message}
      placeholder="Enter your message..."
      name="message"
      required
    />
    <button class="btn">Send Message</button>
  </form>

  {#if isFormSubmitted}
    <p>{thankYou}</p>
  {/if}

  {#if error}
    <p class:error>There was an error. Please try again.</p>
  {/if}
</div>

<style>
  div {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 80%;
    max-width: 400px;
    margin: 4em 0;
  }
  h3 {
    color: #fb0;
  }
  p {
    color: white;
  }
  form {
    width: 100%;
  }
  input,
  textarea {
    display: block;
    width: 100%;
    margin: 1em 0;
    padding: 1em;
    border-radius: 4px;
  }
  textarea {
    min-height: 200px;
  }
  button {
    width: 100%;
    border-radius: 4px;
  }
  .error {
    color: white;
  }
</style>
