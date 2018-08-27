
<template>
      <section class="about">
        <div class="container">
            <div class="row">
                <div class="offset-xl-1 col-xl-3 col-lg-4 col-md-12 col-sm-12 text-center-sm showcase-left1">
                    <img src="../assets/Page1.png" alt="icon" class="desc-dot">
                    <h3 class="heading__teritary heading__teritary--about ">Track your expenses.
                        <br> Quickly.
                    </h3>
                    <p class="text__secondary text__secondary--about">While it’s important that you decide what you want your money to do now, it’s more important to realize.</p>
                </div>
                <div class="offset-xl-1 col-xl-3 col-lg-4 col-md-12 col-sm-12 text-center-sm mt-mb-md showcase-left2">
                    <img src="../assets/Page2.png" alt="icon">
                    <h3 class="heading__teritary heading__teritary--about ">Analyse your Expenses.
                        <br> On every device.
                    </h3>
                    <p class="text__secondary text__secondary--about">We can’t believe this has to be a rule, because, of course, when you need to change your budget, just
                        change it.</p>
                </div>
                <div class="offset-xl-1 col-xl-3 col-lg-4 col-md-12 col-sm-12 text-center-sm showcase-left3">
                    <img src="../assets/Page3.png" alt="icon">
                    <h3 class="heading__teritary heading__teritary--about ">Set a budget.
                        <br> Start saving money.
                    </h3>
                    <p class="text__secondary text__secondary--about">We don’t want you stressed. So work toward spending money today that you’ve earned at least a month ago.
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
  name: 'About',
};
</script>

<style lang="scss">
.about {
  padding: 150px 0 70px 0;
  @media (max-width: 767.98px) {
    padding: 120px 0;
  }
  .container {
    @media (min-width: 1200px) {
      max-width: 1400px;
    }
  }
}
</style>
