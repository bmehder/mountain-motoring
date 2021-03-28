<script>
  let form;

  function formSubmit(e) {
    e.preventDefault();

    const formData = new FormData();
    formData.append("name", document.querySelector('input[name="name"]').value);
    formData.append(
      "email",
      document.querySelector('input[name="email"]').value
    );
    formData.append("message", document.querySelector("textarea").value);

    fetch("https://getform.io/f/{your-form-endpoint}", {
      method: "POST",
      body: formData,
    })
      .then((response) => console.log(response))
      .catch((error) => console.log(error));
  }
</script>

<div>
  <h3>Send Us A Message</h3>
  <form action="#" bind:this={form} on:submit={formSubmit}>
    <input placeholder="Enter your name..." type="text" name="name" />
    <input placeholder="Enter your email..." type="email" name="email" />
    <textarea placeholder="Enter your message..." name="message" />
    <button>Send Message</button>
  </form>
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
