/* eslint-disable */
<template>
  <div id="app">
    <Header />
    <About />
    <Description />
      <section class="carousel d-flex flex-column align-self-center justify-content-center ">
          <div class="container ">
              <h2 class="heading__secondary heading__secondary--clients mb-4">Satisfied Users</h2>
              <p class="text__secondary">We bring together everything from balances and bills to your credit score and more.</p>
          </div>
      </section>
    <CarouselCustomers />
    <Pricing />
    <LogoCarousel />
    <Contact />
    <Footer />
  </div>
</template>

<script>
/* eslint-disable */
import Header from './components/Header';
import About from './components/About';
import Description from './components/Description';
import CarouselCustomers from './components/CarouselCustomers';
import LogoCarousel from './components/LogoCarousel';
import Pricing from './components/Pricing';
import Contact from './components/Contact';
import Footer from './components/Footer';

export default {
  name: 'app',
  components: {
    Header,
    About,
    Description,
    CarouselCustomers,
    Pricing,
    LogoCarousel,
    Footer,
    Contact,
  },
};
</script>

<style lang="scss">
.carousel {
  background: url(./assets/Group3.png);
  min-height: 350px;
  background-size: cover;
  background-repeat: no-repeat;
  padding: 0 0 100px 0;
  border-radius: 4px;
}

@keyframes fromBottom {
  0% {
    opacity: 0;
    transform: translateY(35px);
  }
  100% {
    opacity: 1;
    transform: translate(0);
  }
}

@keyframes Floating {
  0% {
    -webkit-transform: translateY(40px);
  }
  65% {
    -webkit-transform: translate(0);
  }
  100% {
    -webkit-transform: translateY(40px);
  }
}

.anim__head {
  animation-name: fromBottom;
  animation-duration: 1s;
}
.anim__head--2 {
  animation-duration: 1.8s;
}

.anim__head--3 {
  animation-duration: 2s;
}
.floating {
  animation-name: Floating;
  animation-iteration-count: infinite;
  animation-duration: 7s;
}
$color-black: #000;
html {
  font-family: 'Lato', sans-serif;
  box-sizing: border-box;
}
.slick-slide > div {
  margin: 0 15px;
}
body {
  position: relative;
  margin: 20px 0;
  padding: 0 20px;
  background: #fff;
  box-sizing: border-box;
  @media (max-width: 992px) {
    margin: 0;
    padding: 0 !important;
  }
}
.btn-main {
  color: #fff;
  border: none;
  border-radius: 4px;
  background-color: rgb(255, 104, 102);
  width: 179px;
  height: 54px;
  @media (max-width: 576px) {
    width: 100%;
    margin-bottom: 20px;
  }
}
.btn-main--pricing {
  border-width: 1px;
  border-color: rgb(229, 229, 235);
  border-style: solid;
  border-radius: 4px;
  width: 177px;
  height: 52px;
  color: #8491ae;
  background: transparent;
}
.btn-main--pricing:hover {
  background-color: rgb(255, 104, 102);
  color: #fff;
}

.btn:hover {
  box-shadow: 0px 4px 64px 0px rgba(32, 38, 59, 0.15);
}
.btn-second {
  color: #fff;
  border-radius: 4px;
  background-color: rgb(45, 70, 201);
  width: 220px;
  height: 54px;
  margin-left: 15px;
  display: inline-flex;
  align-items: center;
  text-align: center;
  justify-content: center;
  border: none;
  @media (max-width: 576px) {
    width: 100%;
    margin-left: 0;
  }
  img {
    margin-right: 20px;
  }
}

.ctr-abs {
  position: absolute;
  top: 50%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%);
  text-align: left;
}

ul {
  list-style-type: none !important;
  padding: 0;
}

.pall-35 {
  padding: 35px;
}

.mt-100 {
  margin-top: 100px;
  @media (max-width: 992px) {
    margin-top: 80px;
  }
}

.mt-170 {
  margin-top: 170px;
  @media (max-width: 992px) {
    margin-top: 80px;
  }
}

.text-center-sm {
  @media (max-width: 992px) {
    text-align: center;
  }
}

.text-center-mid {
  @media (max-width: 992px) {
    text-align: center !important;
  }
}

.mt-mb-md {
  @media (max-width: 992px) {
    margin: 55px 0;
  }
}

.mb-sm-mb {
  @media (max-width: 576px) {
    margin-bottom: 25px;
  }
}

.footer-col {
  @media (max-width: 576px) {
    flex-direction: column;
  }
}

.dn-tbl {
  @media (max-width: 992px) {
    display: none !important;
  }
}

.heading {
  backface-visibility: hidden;
}
.heading__primary {
  font-size: 60px;
  font-weight: normal;
  @media (max-width: 992px) {
    font-size: 50px;
  }
  @media (max-width: 576px) {
    font-size: 35px;
  }
}
.heading__secondary {
  font-weight: normal;
  font-size: 50px;
  color: #404355;
  @media (max-width: 576px) {
    font-size: 35px;
  }
}
.heading__secondary--clients {
  color: #fff;
  max-width: 560px;
  margin-top: 70px;
  @media (max-width: 576px) {
    margin-top: 0px;
  }
}
.heading__teritary {
  font-size: 23px;
  color: #404355;
  font-weight: normal;
}
.heading__teritary--about {
  margin: 15px 0 25px 0;
}
.heading__teritary--get {
  font-size: 32px;
}
.text__primary {
  font-size: 18px;
}
.text__primary--header {
  margin: 35px 0;
  max-width: 600px;
  @media (max-width: 992px) {
    max-width: 100%;
  }
}
.text__secondary {
  font-size: 16px;
  color: #8491ae;
}

.text__secondary--desc {
  @media (min-width: 992px) {
    max-width: 700px;
    margin: 30px auto 0 auto;
  }
}
.text__teritary {
  font-size: 14px;
  color: #8491ae;
}

.text__secondary--about {
  @media (max-width: 767.98px) {
    max-width: 100%;
  }
}
</style>
