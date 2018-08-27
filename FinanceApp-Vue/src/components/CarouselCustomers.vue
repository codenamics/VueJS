<template>
    <div class="container">
            <div >
          <slick
            ref="slick"
            :options="slickOptions"
            class="carousel__row"
          >
   <div class="carousel__row-box">
                    <div class="box-top">
                        <img src="../assets/Screen Shot 2016-05-13 at 21.01.27.png" alt="face">
                        <div class="id">
                            <span class="name">David Houston</span>
                            <span class="comp">BRANDTYPE</span>
                        </div>
                    </div>
                    <p class="text__teritary">Excellent this is exactly what I have been looking for! I don’t need all of the fancy finance stuff,
                        just a simple way to see...</p>
                </div>
                <div class="carousel__row-box">
                    <div class="box-top">
                        <img src="../assets/Screen Shot 2016-05-13 at 21.01.27.png" alt="face">
                        <div class="id">
                            <span class="name">David Houston</span>
                            <span class="comp">BRANDTYPE</span>
                        </div>
                    </div>
                    <p class="text__teritary">Excellent this is exactly what I have been looking for! I don’t need all of the fancy finance stuff,
                        just a simple way to see...</p>
                </div>
                <div class="carousel__row-box">
                    <div class="box-top">
                        <img src="../assets/Screen Shot 2016-05-13 at 21.01.27.png" alt="face">
                        <div class="id">
                            <span class="name">David Houston</span>
                            <span class="comp">BRANDTYPE</span>
                        </div>
                    </div>
                    <p class="text__teritary">Excellent this is exactly what I have been looking for! I don’t need all of the fancy finance stuff,
                        just a simple way to see...</p>
                </div>
                <div class="carousel__row-box">
                    <div class="box-top">
                        <img src="../assets/Screen Shot 2016-05-13 at 21.01.27.png" alt="face">
                        <div class="id">
                            <span class="name">David Houston</span>
                            <span class="comp">BRANDTYPE</span>
                        </div>
                    </div>
                    <p class="text__teritary">Excellent this is exactly what I have been looking for! I don’t need all of the fancy finance stuff,
                        just a simple way to see...</p>
                </div>
                <div class="carousel__row-box">
                    <div class="box-top">
                        <img src="../assets/Screen Shot 2016-05-13 at 21.01.27.png" alt="face">
                        <div class="id">
                            <span class="name">David Houston</span>
                            <span class="comp">BRANDTYPE</span>
                        </div>
                    </div>
                    <p class="text__teritary">Excellent this is exactly what I have been looking for! I don’t need all of the fancy finance stuff,
                        just a simple way to see...</p>
                </div>
</slick>
            </div>
        </div>
</template>

<script>
import Slick from 'vue-slick';
export default {
  name: 'CarouselCustomers',
  components: {
    Slick,
  },
  // eslint-disable-next-line
  data() {
    return {
      slickOptions: {
        autoplay: true,
        autoplaySpeed: 4000,
        slidesToShow: 3,
        slidesToScroll: 3,
        dots: false,
        arrows: false,
        responsive: [
          {
            breakpoint: 990,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 2,
            },
          },
          {
            breakpoint: 550,
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

<style lang="scss" scoped>
.carousel__row {
  max-width: 1300px;
  margin: 0 auto;
  margin-top: -100px;
  text-align: left;
}
.slick-track {
  padding: 0 0 70px 0;
}
.carousel__row-box {
  border-radius: 4px;
  background-color: #fff;

  padding: 25px;
  box-shadow: 0px 8px 60px -25px rgba(48, 52, 73, 0.267);
  -webkit-box-shadow: 0px 8px 60px -25px rgba(48, 52, 73, 0.267);
  -moz-box-shadow: 0px 8px 60px -25px rgba(48, 52, 73, 0.267);
  p {
    margin-top: 25px;
  }
}

@media (min-width: 1300px) {
  .container {
    max-width: 1300px;
  }
}
.box-top {
  display: grid;
  grid-template-columns: min-content max-content;
  grid-column-gap: 18px;
  img {
    border-radius: 50%;
  }
  .id {
    display: flex;
    flex-direction: column;
    .name {
      color: #404355;
      font-size: 16px;
    }
    .comp {
      color: #1e3bb2;
      font-size: 12px;
    }
  }
}
</style>
