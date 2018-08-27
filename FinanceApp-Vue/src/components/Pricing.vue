
<template>
      <section class="pricing" id="pricing">
        <div class="container">
            <h2 class="heading__secondary heading__secondary--desc text-center">Pricing</h2>
            <p class="text__secondary text__secondary--desc text-center">Get started for free, or have multiple calendars right from the beginning. Explore our monthly and yearly plans
                and pick the one that best suits your needs.</p>
            <div class="row mt-100">
                <div class="col-xl-4 col-lg-4 col-md-12 col-sm-12 text-center">
                    <div class="pall-35 d-flex flex-column justify-content-between pricing__box t2">
                        <h3 class="heading__teritary">Starter Plan</h3>
                        <span class="pricing__price">Free</span>
                        <span class="pricing__period">MONTH</span>
                        <p class="text__teritary">The easiest way to get started with Dollarbird for everyone.</p>
                        <a href="">
                            <button class="btn btn-main--pricing"> Start Now</button>
                        </a>
                    </div>
                </div>
                <div class="col-xl-4 col-lg-4 col-md-12 col-sm-12 text-center mt-mb-md">
                    <div class="pall-35 d-flex flex-column justify-content-between pricing__box pricing__box--active t1">
                        <h3 class="heading__teritary">Enterprise Plan</h3>
                        <span class="pricing__price pricing__price--active">$19.00 </span>
                        <span class="pricing__period">MONTH</span>
                        <p class="text__teritary">Unlimited for 15 Users. Advanced collaborative option for partners, families, freelancers.</p>
                        <a href="">
                            <button class="btn btn-main"> Start Now</button>
                        </a>
                    </div>
                </div>
                <div class="col-xl-4 col-lg-4 col-md-12 col-sm-12 text-center">
                    <div class="pall-35 d-flex flex-column justify-content-between pricing__box t2">
                        <h3 class="heading__teritary">Unlimited Plan</h3>
                        <span class="pricing__price">$39.00</span>
                        <span class="pricing__period">MONTH</span>
                        <p class="text__teritary">Collaborative financial tracking and planning for small businesses and enterprises.</p>
                        <a href="">
                            <button class="btn btn-main--pricing"> Start Now</button>
                        </a>
                    </div>

                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
  name: 'Pricing',
};
</script>

<style lang="scss">
.pricing {
  padding: 100px 0;
  background: url(../assets/RectangleCopy5.png);
  margin: 0 -20px;
  background-size: cover;
  background-position: center;
  @media (max-width: 992px) {
    margin: 0;
    padding-top: 35px;
  }
  .pricing__box {
    border-radius: 4px;
    max-width: 345px;
    height: 425px;
    margin: 0 auto;
    &--active {
      box-shadow: 12.622px 12.829px 114px 0px rgba(48, 52, 73, 0.13);
    }
  }
  .pricing__price {
    color: #404355;
    font-size: 50px;
    .pricing__price--active {
      color: #ff6866;
    }
  }
  .pricing__period {
    color: #1e3bb2;
    font-size: 9px;
    transform: translateY(-20px);
  }
}
</style>
