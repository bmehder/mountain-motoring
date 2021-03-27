<div>
  <h3>Send Us A Message</h3>
  <form on:submit|preventDefault>
    <input placeholder="Enter your name" type="text" />
    <input placeholder="Enter your email..." type="email" />
    <input placeholder="Enter your zip code..." type="text" />
    <textarea placeholder="Enter your message..." />
    <button>Send Message</button>
  </form>
</div>

<style>
  div {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 400px;
    margin: 4em 0;
  }
  form {
    width: 100%;
  }
  input,
  textarea,
  button {
    display: block;
    width: 100%;
    margin: 1em;
    padding: 1em;
  }
  textarea {
    min-height: 200px;
  }
  button {
    background: gold;
    color: #444;
    font-weight: bold;
    outline: none;
    border: none;
  }
</style>
