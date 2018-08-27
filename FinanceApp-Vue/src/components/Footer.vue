<template>
    <footer class="footer" id="blog">
        <div class="container">
            <div class="row text-center-sm">
                <div class="col-xl-2 col-lg-2 col-md-2">
                    <img src="../assets/logo.png" alt="logo" class="img-fluid">
                </div>
                <div class="offset-xl-1 col-xl-2 col-md-2 footer__list">
                    <h5 class="footer__list--head">Company</h5>
                    <ul class="footer__list--list">
                        <li>
                            <a class="text-muted" href="#"> About Us</a>
                        </li>
                        <li>
                            <a class="text-muted" href="#">Press</a>
                        </li>
                        <li>
                            <a class="text-muted" href="#">Reviews</a>
                        </li>
                    </ul>
                </div>
                <div class="col-xl-2 col-md-2">
                    <h5 class="footer__list--head">Blog</h5>
                    <ul class="footer__list--list">
                        <li>
                            <a class="text-muted" href="#"> Finances</a>
                        </li>
                        <li>
                            <a class="text-muted" href="#">Technology</a>
                        </li>
                        <li>
                            <a class="text-muted" href="#"> Mobile</a>
                        </li>
                    </ul>
                </div>
                <div class="col-xl-2 col-md-2">
                    <h5 class="footer__list--head">Integrations</h5>
                    <ul class="footer__list--list">
                        <li>
                            <a class="text-muted" href="#"> Web App</a>
                        </li>
                        <li>
                            <a class="text-muted" href="#"> Android App</a>
                        </li>
                        <li>
                            <a class="text-muted" href="#">iOS App</a>
                        </li>
                        <li>
                            <a class="text-muted" href="#"> Play Station</a>
                        </li>
                    </ul>
                </div>
                <div class="offset-xl-2 col-xl-1 offset-md-2 col-md-2">
                    <h5 class="footer__list--head">Get social</h5>
                    <ul class="footer__list--list d-flex justify-content-center">
                        <li>
                            <a class="text-muted social" href="#">
                                <img src="../assets/Fill 1.png" alt="logo">
                            </a>
                        </li>
                        <li class="">
                            <a class="text-muted social" href="#">
                                <img src="../assets/twit.png" alt="logo">
                            </a>
                        </li>
                        <li>
                            <a class="text-muted social" href="#">
                                <img src="../assets/you.png" alt="logo">
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
export default {
  name: 'Footer',
};
</script>

<style lang="scss">
.footer {
  padding: 80px 0 100px 0;
}
.text-muted {
  font-size: 14px;
  color: #8491ae;
}
.footer__list {
  font-size: 14px;
}

.footer__list--head {
  color: #404355;
  font-weight: 500;
  margin-bottom: 20px;
}
.footer__list--list {
  li {
    margin: 10px 0;
  }
}
.social {
  margin: 0 15px;
}
</style>
