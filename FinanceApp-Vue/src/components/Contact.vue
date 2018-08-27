
<template>
      <div class="container" id="contact">
        <div class="row">
            <div class="t2 get__app col-xl-12 text-center d-flex flex-column justify-content-center">
                <h3 class="heading__teritary heading__teritary--get">Get a Finance Banking App now</h3>
                <p class="text__teritary mt-2">No contact, no set-up costs, just awesome way to organise your money.</p>
                <div class="d-flex footer-col justify-content-center  align-items-center cta mt-2">
                    <button class="btn btn-main"> Start Now</button>
                    <p class="view-price">or you can
                        <a href="" class="view-price--href">View pricing</a>
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Contact',
};
</script>

<style lang="scss">
.get__app {
  padding: 60px 15px;
  margin-top: -160px;
  min-height: 250px;
  border-radius: 4px;
  background-color: rgb(255, 255, 255);
  box-shadow: 59.622px 51.829px 114px 0px rgba(48, 52, 73, 0.13);
}
.view-price {
  margin: 0 0 0 25px;
}
.get__app--href {
  color: #ff6866;
}
</style>
