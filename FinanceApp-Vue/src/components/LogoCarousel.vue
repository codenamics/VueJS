<template>
  <section class="clients d-flex flex-column align-items-center">
        <h1 class="heading__secondary heading__secondary--clients">Join thousands of independent business</h1>
        <div class="container">
            <Slick
            ref="slick"
            :options="slickOptions"
             class="clients__row d-flex align-items-center align-self-center justify-content-center">
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/Shape.png" alt="logo" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/microsoft-azure.png" alt="" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/linkedin.png" alt="logo" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/barbour-64875.png" alt="logo" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/samsung-1.png" alt="logo" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/Shape.png" alt="logo" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/microsoft-azure.png" alt="logo" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/linkedin.png" alt="logo" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/barbour-64875.png" alt="logo" class="img-fluid">
                </div>
                <div class="client__logo d-flex align-items-center">
                    <img src="../assets/samsung-1.png" alt="logo" class="img-fluid">
                </div>
            </Slick>
            </div>
    </section>
</template>

<script>
import Slick from 'vue-slick';
export default {
  name: 'LogoCarousel',
  components: {
    Slick,
  },
  // eslint-disable-next-line
  data() {
    return {
      slickOptions: {
        autoplay: true,
        autoplaySpeed: 5000,
        infinite: true,
        slidesToShow: 4,
        slidesToScroll: 4,
        arrows: false,
        dots: false,
        responsive: [
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 3,
              infinite: true,
            },
          },
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 2,
            },
          },
          {
            breakpoint: 480,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
            },
          },
        ],
      },
    };
  },
};
</script>

<style lang="scss">
.clients {
  min-height: 620px;
  background: url(../assets/clients.png);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  text-align: center;
  border-radius: 4px;
  .clients__row {
    min-height: 150px;
    margin-top: 28px;
    img {
      margin: 0 auto;
    }
  }
  .client__logo {
    min-height: 90px;
  }
}
</style>
