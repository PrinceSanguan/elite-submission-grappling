<template>
  <div>
    <section class="slider_section">
      <div
        id="customCarousel1"
        class="carousel slide"
        data-ride="carousel"
        data-interval="false"
      >
        <div class="carousel-inner">
          <!-- Loop through items in the carousel -->
          <div
            v-for="(item, index) in carouselItems"
            :key="index"
            :class="['carousel-item', { active: index === 0 }]"
          >
            <div class="container">
              <div class="row">
                <div class="col-lg-10 col-md-11 mx-auto">
                  <div class="detail-box">
                    <h1>{{ item.title }}</h1>
                    <p>{{ item.description }}</p>
                    <div class="btn-box">
                      <a :href="item.link" class="btn1">Free Trial</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Carousel controls -->
        <div class="carousel_btn-box">
          <a
            class="carousel-control-prev"
            href="#customCarousel1"
            role="button"
            data-slide="prev"
          >
            <i class="fa fa-arrow-left" aria-hidden="true"></i>
            <span class="sr-only">Previous</span>
          </a>
          <a
            class="carousel-control-next"
            href="#customCarousel1"
            role="button"
            data-slide="next"
          >
            <i class="fa fa-arrow-right" aria-hidden="true"></i>
            <span class="sr-only">Next</span>
          </a>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "HeroComponent",
  data() {
    return {
      // List of carousel items with titles, descriptions, and links
      carouselItems: [
        {
          title:
            "Visit SJA in Swansea to Try Martial Arts! BJJ | MMA | Sub Grappling | Self Defence",
          description:
            "SJA in Swansea offers BJJ, MMA, Submission Grappling, and Self Defence. Get fit and learn practical skills - visit SJA today!",
          link: "https://api.leadconnectorhq.com/widget/form/WnUpRHuzuzpPVKrB06JQ?fbclid=IwZXh0bgNhZW0CMTAAAR15AvkwWjlzlJMjzgCVxp7k4_ThTFfwtXRHYBa1aX0Sm2Oi-PnE92nnNlo_aem_gEbqjAZgvYcdaJf8Uk71dA",
        },
        {
          title: "MMA Classes in Swansea",
          description:
            "Experience top-tier MMA training with expert coaches and a supportive community. Beginners and seasoned fighters thrive here. Join us and achieve your goals quickly!",
          link: "https://api.leadconnectorhq.com/widget/form/WnUpRHuzuzpPVKrB06JQ?fbclid=IwZXh0bgNhZW0CMTAAAR15AvkwWjlzlJMjzgCVxp7k4_ThTFfwtXRHYBa1aX0Sm2Oi-PnE92nnNlo_aem_gEbqjAZgvYcdaJf8Uk71dA",
        },
        {
          title: "Self Defence Classes in Swansea",
          description:
            "Our Self-Defense Program for kids teaches safety skills, respect, and self-discipline in a fun way. Enroll your child to give them confidence and essential skills.",
          link: "https://api.leadconnectorhq.com/widget/form/WnUpRHuzuzpPVKrB06JQ?fbclid=IwZXh0bgNhZW0CMTAAAR15AvkwWjlzlJMjzgCVxp7k4_ThTFfwtXRHYBa1aX0Sm2Oi-PnE92nnNlo_aem_gEbqjAZgvYcdaJf8Uk71dA",
        },
        {
          title: "BJJ Classes in Swansea",
          description:
            "Discover Brazilian Jiu-Jitsu, where technique and strategy reign. Our classes cater to all levels, focusing on ground fighting and submissions. Learn from seasoned practitioners in a supportive environment.",
          link: "https://api.leadconnectorhq.com/widget/form/WnUpRHuzuzpPVKrB06JQ?fbclid=IwZXh0bgNhZW0CMTAAAR15AvkwWjlzlJMjzgCVxp7k4_ThTFfwtXRHYBa1aX0Sm2Oi-PnE92nnNlo_aem_gEbqjAZgvYcdaJf8Uk71dA",
        },
        {
          title: "Submission Grappling Classes in Swansea",
          description:
            "Dive into Submission Grappling, where precision and technique are key. Our classes develop advanced skills in submissions and positional control. Join us to enhance your grappling expertise.",
          link: "https://api.leadconnectorhq.com/widget/form/WnUpRHuzuzpPVKrB06JQ?fbclid=IwZXh0bgNhZW0CMTAAAR15AvkwWjlzlJMjzgCVxp7k4_ThTFfwtXRHYBa1aX0Sm2Oi-PnE92nnNlo_aem_gEbqjAZgvYcdaJf8Uk71dA",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Add your custom styles here for the carousel */
</style>
