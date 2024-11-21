<template>
  <div>
    <section class="client_section layout_padding" id="testimonials">
      <div class="container">
        <div class="heading_container heading_center">
          <h2 style="color: #ffffff">TESTIMONIALS</h2>
        </div>
        <div
          id="carouselExample2Controls"
          class="carousel slide"
          data-ride="carousel"
        >
          <div class="carousel-inner">
            <div class="carousel-item active">
              <div class="row">
                <div class="col-lg-7 col-md-9 mx-auto">
                  <div class="client_container">
                    <div class="details-box">
                      <h3
                        style="
                          color: #fffdfd;
                          text-decoration: underline solid red;
                          text-underline-offset: 10px;
                          padding-bottom: 5px;
                          display: inline-block;
                        "
                      >
                        James Evans
                      </h3>
                      <p style="color: #fffdfd">
                        I trained here as a visitor and was really impressed
                        with both the atmosphere and the level of coaching.
                        Classes are well structured for all levels and the
                        principles are well explained with each technique, which
                        will give students a deeper understanding over time.
                        Everyone I’ve met from the coaches to the students have
                        been friendly and welcoming and I look forward to coming
                        back again in the future. Highly recommend SJA to anyone
                        and everyone in the area.
                      </p>
                      <span>
                        <i class="fa fa-quote-left" aria-hidden="true"></i>
                      </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="carousel-item">
              <div class="row">
                <div class="col-lg-7 col-md-9 mx-auto">
                  <div class="client_container">
                    <div class="details-box">
                      <h3
                        style="
                          color: #fffdfd;
                          text-decoration: underline solid red;
                          text-underline-offset: 10px;
                          padding-bottom: 5px;
                          display: inline-block;
                        "
                      >
                        Damien Hann
                      </h3>
                      <p style="color: #fffdfd">
                        This place is a great place to learn Martial Arts. Been
                        going there almost 5 years now and a lot has changed,
                        great staff and spacious gym. Overall it's a great place
                        and I recommend you try it!
                      </p>
                      <span>
                        <i class="fa fa-quote-left" aria-hidden="true"></i>
                      </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="carousel-item">
              <div class="row">
                <div class="col-lg-7 col-md-9 mx-auto">
                  <div class="client_container">
                    <div class="details-box">
                      <h3
                        style="
                          color: #fffdfd;
                          text-decoration: underline solid red;
                          text-underline-offset: 10px;
                          padding-bottom: 5px;
                          display: inline-block;
                        "
                      >
                        Emma Owen
                      </h3>
                      <p style="color: #fffdfd">
                        My son loved it! He can't wait to go again. Really
                        informative and helpful staff. They seem very organised
                        and professional
                      </p>
                      <span>
                        <i class="fa fa-quote-left" aria-hidden="true"></i>
                      </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="carousel_btn-box">
            <a
              class="carousel-control-prev"
              href="#carouselExample2Controls"
              role="button"
              data-slide="prev"
            >
              <span>
                <i class="fa fa-arrow-left" aria-hidden="true"></i>
              </span>
              <span class="sr-only">Previous</span>
            </a>
            <a
              class="carousel-control-next"
              href="#carouselExample2Controls"
              role="button"
              data-slide="next"
            >
              <span>
                <i class="fa fa-arrow-right" aria-hidden="true"></i>
              </span>
              <span class="sr-only">Next</span>
            </a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default { name: "ClientComponent" };
</script>

<style>
.client_section {
  padding: 20px 0;
  position: relative;
  background: #000;
}

.client_section::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.client_container {
  display: flex;
  gap: 20px;
  align-items: center;
  justify-content: center;
}

.details-box {
  text-align: center; /* Existing rule */
  max-height: 250px; /* Set a maximum height */
  overflow-y: auto; /* Enable vertical scrolling if needed */
}

.details-box h3 {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

.details-box p {
  font-size: 18px;
  line-height: 1.6;
  margin-bottom: 20px;
}

.carousel_btn-box {
  text-align: center;
  margin-top: 20px;
}

.carousel-control-prev,
.carousel-control-next {
  color: #fff;
  font-size: 24px;
  width: auto;
  height: auto;
  background-color: transparent;
}

.carousel-control-prev {
  left: -50px;
}

.carousel-control-next {
  right: -50px;
}

.carousel-control-prev-icon,
.carousel-control-next-icon {
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  padding: 10px;
}

.carousel-control-prev-icon {
  margin-right: 5px;
}

.carousel-control-next-icon {
  margin-left: 5px;
}

@media (max-width: 768px) {
  .client_container {
    flex-direction: column;
  }

  .carousel-control-prev,
  .carousel-control-next {
    left: 0;
    right: 0;
    top: -40px;
  }
}
</style>
