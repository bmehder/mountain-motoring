<script>
  let form;
  let name;
  let email;
  let message;
  let isSubmitted = false;
  const thankYou =
    "Thank you for submitting your message. We will get back to you as soon as possible.";

  function formSubmit(e) {
    e.preventDefault();

    const formData = new FormData();
    formData.append("name", document.querySelector('input[name="name"]').value);
    formData.append(
      "email",
      document.querySelector('input[name="email"]').value
    );
    formData.append("message", document.querySelector("textarea").value);

    fetch("https://getform.io/f/0615fe82-acf6-4e9b-8ba3-902a0309da6d", {
      method: "POST",
      body: formData,
    })
      .then((response) => {
        console.log(response);
        isSubmitted = true;
      })
      .catch((error) => console.log(error));

    name.value = "";
    email.value = "";
    message.value = "";
  }
</script>

<div>
  <h3>Send Us A Message</h3>
  <form bind:this={form} on:submit={formSubmit}>
    <input
      bind:this={name}
      placeholder="Enter your name..."
      type="text"
      name="name"
      required
    />
    <input
      bind:this={email}
      placeholder="Enter your email..."
      type="email"
      name="email"
      required
    />
    <textarea
      bind:this={message}
      placeholder="Enter your message..."
      name="message"
      required
    />
    <button>Send Message</button>
  </form>
  {#if isSubmitted}
    <p>{thankYou}</p>
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
    color: gold;
  }
  p {
    color: white;
  }
  form {
    width: 100%;
  }
  input,
  textarea,
  button {
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
    background: gold;
    font-weight: bold;
    outline: none;
    border: none;
    transition: transform 300ms;
  }
  button:hover {
    transform: scale(0.98);
  }
</style>
