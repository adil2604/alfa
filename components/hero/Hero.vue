<template>
  <div class="container">
    <div class="hero-body">
      <b-carousel
        id="carousel-1"
        :interval="4000"
        controls
        indicators
        background="#ababab"
        img-width="1024"
        img-height="480"
        style="text-shadow: 1px 1px 2px #333;"
      >
        <!-- Text slides with image -->
        <b-carousel-slide
          img-src="../../static/slider1.jpg"
        >
          <p>
            Apple Watch Series 6
            уже в продаже!<br>
            <b-button variant="primary">Заказать</b-button>
          </p>
        </b-carousel-slide>

        <!-- Slides with custom text -->
        <b-carousel-slide img-src="../../static/slider2.jpg">
        </b-carousel-slide>

      </b-carousel>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.hero {
  background: url("../../static/slider1.png") no-repeat;
  background-position: center;
}

h1, h2 {
  color: #fff;
}
</style>
