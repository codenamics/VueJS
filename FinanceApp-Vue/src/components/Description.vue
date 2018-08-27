<template>
     <section class="desc" id="service">
        <div class="container">
            <h2 class="heading__secondary heading__secondary--desc text-center">The Most Efficient Finance Tool</h2>
            <p class="text__secondary text__secondary--desc text-center">Simple and fast alternative to feature-rich, complex budget planner / personal finance apps. There are no categories
                to manage, no charts to interpret and no learning curve.</p>
            <div class="row mt-170">
                <div class="col-xl-3 col-lg-3 col-md-12 col-sm-12 text-right text-center-mid">
                    <div class="desc-dot desc-dot--right pulse showcase-left1"></div>
                    <h3 class="heading__teritary showcase-left1">Secure Transfers</h3>
                    <p class="text__secondary mb-5 showcase-left1">Take control over your personal finances: keep track of your expenses</p>
                    <div class="desc-dot desc-dot--right pulse showcase-left2"></div>
                    <h3 class="heading__teritary showcase-left2">Fast and Simple Setup</h3>
                    <p class="text__secondary mb-5 showcase-left2">Take control over your personal finances: keep track of your expenses</p>
                    <div class="desc-dot desc-dot--right pulse showcase-left3"></div>
                    <h3 class="heading__teritary showcase-left3">Everything in One Place</h3>
                    <p class="text__secondary mb-5 showcase-left3">Take control over your personal finances: keep track of your expenses</p>
                </div>
                <div class="col-xl-6 col-lg-6 col-md-12 col-sm-12 text-center mb-sm-mb floating">
                    <img src="../assets/iPhne 6.png" alt="phone" class="img-fluid iphone-app">
                </div>
                <div class="col-xl-3 col-lg-3 col-md-12 col-sm-12 text-left text-center-mid">
                    <div class="desc-dot pulse showcase-right1"></div>
                    <h3 class="heading__teritary showcase-right1">Customized Registration</h3>
                    <p class="text__secondary mb-5 showcase-right1">Take control over your personal finances: keep track of your expenses</p>
                    <div class="desc-dot pulse showcase-right2"></div>
                    <h3 class="heading__teritary showcase-right2">Quick and Efortless</h3>
                    <p class="text__secondary mb-5 showcase-right2">Take control over your personal finances: keep track of your expenses</p>
                    <div class="desc-dot pulse showcase-right3"></div>
                    <h3 class="heading__teritary showcase-right3">Apple Watch App</h3>
                    <p class="text__secondary mb-5 showcase-right3">Take control over your personal finances: keep track of your expenses</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
  name: 'Description',
};
</script>

<style lang="scss">
.desc {
  padding: 100px 0 50px 0;
  background: url(../assets/RectangleCopy5.png);
  margin: 0 -20px;
  background-size: cover;
  background-position: center;
  @media (max-width: 992px) {
    margin: 0;
  }
  @media (max-width: 576px) {
    padding-top: 20px;
  }
  .iphone-app {
    @media (min-width: 992px) {
      transform: translateY(-120px);
    }
  }
  .desc-dot {
    border-radius: 50%;
    background-image: linear-gradient(
      -90deg,
      rgb(62, 77, 222) 0%,
      rgb(41, 57, 196) 100%
    );
    width: 10px;
    height: 10px;
    margin-bottom: 15px;
    box-shadow: 0px 10px 20px 0px rgba(15, 68, 255, 0.44);
    @media (max-width: 992px) {
      margin-left: auto;
      margin-right: auto;
    }
    &--right {
      margin-left: auto;
    }
  }
}
</style>
