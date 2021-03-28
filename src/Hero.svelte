<div class="hero">
  <h2>Mountain Motoring</h2>
  <h3>
    September 10th - 12th <br />
    Highlands, NC
  </h3>
</div>

<style>
  .hero {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 660px;
    padding: 2em;
    background: url(https://source.unsplash.com/random/) no-repeat center
      center/cover;
    text-align: center;
    overflow: hidden;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
  }
  .hero::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.2);
  }
  .hero > * {
    z-index: 1;
  }
  h2 {
    text-align: center;
    font-weight: 700;
    font-size: 8vw;
    line-height: 1.25em;
    color: gold;
  }
  h3 {
    font-size: 4vw;
    line-height: 1.5em;
  }
  @media (max-width: 840px) {
    h2 {
      font-size: 15vw;
    }
    h3 {
      margin-top: 1em;
      font-size: 6vw;
    }
  }
</style>
