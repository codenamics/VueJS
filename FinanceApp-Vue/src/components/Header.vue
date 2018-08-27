<template>
     <header class="header">
        <div class="nav-toogle fixed-top" id="nav-scroll">
            <div class="container-fluid container-fluid-nav">
                <nav class="navbar navbar-expand-lg navbar-light justify-content-between">
                    <a class="navbar-brand" href="#">
                        <img src="../assets/logo.png" alt="logo" class="logo-img">
                    </a>
                    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false"
                        aria-label="Toggle navigation">
                        <span class="navbar-toggler-icon"></span>
                    </button>
                    <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
                        <ul class="navbar-nav ">
                            <li class="nav-item active">
                                <a class="nav-link" href="#home" id="nav-link">Homepage
                                    <span class="sr-only">(current)</span>
                                </a>
                            </li>
                            <li class="nav-item active">
                                <a class="nav-link" href="#service" id="nav-link">Services
                                    <span class="sr-only">(current)</span>
                                </a>
                            </li>
                            <li class="nav-item active">
                                <a class="nav-link" href="#pricing" id="nav-link"> Pricing
                                    <span class="sr-only">(current)</span>
                                </a>
                            </li>
                            <li class="nav-item active">
                                <a class="nav-link" href="#blog" id="nav-link">Blog
                                    <span class="sr-only">(current)</span>
                                </a>
                            </li>
                            <li class="nav-item active">
                                <a class="nav-link" href="#contact" id="nav-link">Contact
                                    <span class="sr-only">(current)</span>
                                </a>
                            </li>
                            <li class="nav-item active">
                                <a class="nav-link" href="#contact" id="nav-link">
                                    <button class="btn btn-nav">Start Now</button>
                                    <span class="sr-only">(current)</span>

                                </a>
                            </li>
                        </ul>
                    </div>
                </nav>
            </div>
        </div>
        <div class="container-fluid ctr-abs" id="home">
            <div class="row align-items-center">
                <div class="offset-lg-1 col-lg-6 col-md-12 text-white text-center-mid ">
                    <h1 class="heading__primary anim__head">Manage all your customer support in one place</h1>
                    <p class="text__primary text__primary--header anim__head anim__head--2">Take control over your personal finances: keep track of your expenses. Get to know your spending patterns
                        and prevent money from leaking.</p>
                    <a href="" class="anim__head anim__head--3">
                        <button class="btn btn-main"> Start Now</button>
                    </a>
                    <a href="" class="anim__head anim__head--3">
                        <button class="btn btn-second">
                            <img src="../assets/video-btn.png" alt="video-button">Watch the Video
                        </button>
                    </a>
                </div>
                <div class="col-lg-5 d-flex justify-content-end dn-tbl floating">
                    <img src="../assets/iphone-head.png" alt="iphone" class="iphone-head ">
                </div>
            </div>
        </div>

    </header>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    // eslint-disable-next-line
    handleScroll() {
      const navToogle = document.getElementById('nav-scroll');
      const navBar = document.getElementsByClassName('navbar')[0];
      const navLink = document.getElementsByClassName('nav-link');

      const currentScroll = Math.round(
        window.scrollY /
          (document.documentElement.offsetHeight - window.innerHeight) *
          100
      );
      if (currentScroll === 0) {
        navToogle.style.background = 'transparent';
        for (let i = 0; i < navLink.length; i++) {
          navLink[i].style.color = '#fff';
        }
        navBar.style.padding = '40px 0';
      } else if (currentScroll > 0) {
        for (let i = 0; i < navLink.length; i++) {
          navLink[i].style.color = '#000';
        }
        navToogle.style.background = '#fff';
        navBar.style.padding = '15px 0';
      }
    },
  },
  // eslint-disable-next-line
  created() {
    window.addEventListener('scroll', this.handleScroll);
  },
  // eslint-disable-next-line
  destroyed() {
    window.removeEventListener('scroll', this.handleScroll);
  },
};
</script>

<style lang="scss">
.navbar {
  padding: 40px 0;
  transition: all 0.5s ease-in-out;
}

.nav-toogle {
  background: transparent;
  width: 100%;
  z-index: 1000;
}

.navbar-nav li {
  text-align: center;
  font-size: 14px;
}

.navbar-light .navbar-nav .active > .nav-link {
  color: #fff;
  margin: 0 15px;
}

.navbar-light .navbar-toggler {
  border: none;
}

.logo-img {
  width: 100%;
  margin-left: 30px;
  @media (max-width: 992px) {
    display: none !important;
  }
}

.pad-t-nav {
  padding: 33px 0;
}

.nav-white {
  background: #fff !important;
  li a {
    color: #000 !important;
  }
}

.container-fluid-nav {
  padding: 0 30px;
}

.btn-nav {
  color: #fff;
  border-radius: 4px;
  background-color: rgb(45, 70, 201);
  width: 142px;
  height: 54px;
}

.navbar-expand-lg .navbar-nav {
  @media (max-width: 992px) {
    flex-direction: column;
    align-items: center;
  }
  flex-direction: row;
  align-items: center;
}
.header {
  background: url(../assets/background-head.png);
  height: 95vh;
  min-height: 900px;
  background-size: cover;
  background-position: center;
  color: #fff;
  position: relative;
  border-radius: 4px;
  border: none;
  @media (max-width: 576px) {
    min-height: 0;
    height: 100vh;
  }
}

.iphone-head {
  transform: translateY(135px);
  margin-right: -35px;
  height: 950px;
  @media (max-width: 1199.98px) {
    height: 750px;
  }
}
</style>
