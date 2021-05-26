<img src="/images/gallery-1.jpg" alt="Gallery 1" />
<img src="/images/gallery-2.jpg" alt="Gallery 2" />
<img src="/images/gallery-3.jpg" alt="Gallery 3" />
<img src="/images/gallery-4.jpg" alt="Gallery 4" />
<img src="/images/gallery-5.jpg" alt="Gallery 5" />
<img src="/images/gallery-6.jpg" alt="Gallery 6" />
<img src="/images/gallery-7.jpg" alt="Gallery 7" />
<img src="/images/gallery-8.jpg" alt="Gallery 8" />

<style>
  img {
    display: block;
    width: 25%;
    height: 25%;
    filter: grayscale(100%);
    transition: all 1000ms;
    cursor: pointer;
  }
  img:hover {
    filter: grayscale(0%);
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.24);
    transform: scale(1.05);
    z-index: 1;
    border-radius: 8px;
  }
</style>
