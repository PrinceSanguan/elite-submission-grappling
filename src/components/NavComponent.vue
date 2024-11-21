<template>
  <div class="hero_area">
    <div class="hero_bg_box"></div>

    <!-- Header Section -->
    <header class="header_section">
      <!-- Top Header -->
      <div class="header_top">
        <div class="container-fluid header_top_container">
          <div class="contact_nav">
            <a href="/contact#location" aria-label="View our location">
              <i class="fa fa-map-marker" aria-hidden="true"></i>
              <span
                >Gym: Crayford Weights & Fitness, Unit 3 Retail Park, 3-5 Tower
                Park Rd</span
              >
            </a>
            <a href="#" id="bookingLink" aria-label="Call us">
              <i class="fa fa-phone" aria-hidden="true"></i>
              <span>Call : 0333 242 3919</span>
            </a>
            <a href="/contact" aria-label="Email us">
              <i class="fa fa-envelope" aria-hidden="true"></i>
              <span>contact-us@elitejiujitsultd@gmail.com</span>
            </a>
          </div>
          <div class="social_box">
            <a
              href="https://m.facebook.com/ELIITEJiuJitsu"
              target="_blank"
              aria-label="Follow us on Facebook"
            >
              <i class="fa fa-facebook" aria-hidden="true"></i>
            </a>
            <a
              href="https://x.com/sarujujitsu"
              target="_blank"
              aria-label="Follow us on Twitter"
            >
              <i class="fa fa-times" aria-hidden="true"></i>
            </a>
            <a
              href="https://www.instagram.com/elitesubmissiongrappling/"
              target="_blank"
              aria-label="Follow us on Instagram"
            >
              <i class="fa fa-instagram" aria-hidden="true"></i>
            </a>
          </div>
        </div>
      </div>

      <!-- Bottom Header -->
      <div class="header_bottom">
        <div class="container-fluid">
          <nav class="navbar navbar-expand-lg custom_nav-container">
            <a class="navbar-brand" href="/">ESG Martial Arts</a>
            <button
              class="navbar-toggler"
              type="button"
              data-toggle="collapse"
              data-target="#navbarSupportedContent"
              aria-controls="navbarSupportedContent"
              aria-expanded="false"
              aria-label="Toggle navigation"
            >
              <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
              <ul class="navbar-nav">
                <li class="nav-item active">
                  <a class="nav-link" href="/neath">Neath</a>
                </li>
                <li class="nav-item active">
                  <a class="nav-link" href="/"
                    >Home <span class="sr-only">(current)</span></a
                  >
                </li>
                <li
                  class="nav-item dropdown"
                  v-for="menu in menus"
                  :key="menu.id"
                >
                  <a
                    class="nav-link dropdown-toggle"
                    href="#"
                    role="button"
                    data-toggle="dropdown"
                    aria-haspopup="true"
                    aria-expanded="false"
                  >
                    {{ menu.name }}
                  </a>
                  <div class="dropdown-menu">
                    <a
                      v-for="submenu in menu.submenus"
                      :key="submenu.id"
                      class="dropdown-item"
                      :href="submenu.link"
                    >
                      {{ submenu.name }}
                    </a>
                  </div>
                </li>
                <li class="nav-item active">
                  <a class="nav-link" href="/timetable">Timetable</a>
                </li>
              </ul>
            </div>
          </nav>
        </div>
      </div>
    </header>

    <!-- Pre-loader -->
    <div id="preloader" v-if="showPreloader">
      <img src="/images/saru_logo.ico" alt="SJAMA" />
    </div>
  </div>
</template>

<script>
export default {
  name: "NavComponent",
  data() {
    return {
      showPreloader: false,
      menus: [
        {
          id: 1,
          name: "MMA Programme",
          submenus: [
            { id: 1, name: "Kids Classes", link: "/mma/for/kids" },
            { id: 2, name: "Adults Classes", link: "/mma/for/adults" },
          ],
        },
        {
          id: 2,
          name: "BJJ Programme",
          submenus: [
            { id: 1, name: "Kids Classes", link: "/bjj/for/kids" },
            { id: 2, name: "Adults Classes", link: "/bjj/for/adults" },
          ],
        },
        // Add more menus here
      ],
    };
  },
  methods: {
    redirectToBooking() {
      this.showPreloader = true;
      setTimeout(() => {
        window.location.href =
          "https://api.leadconnectorhq.com/widget/booking/8jZ5oSdq6UlUmh3UbsBK?backgroundColor=%23ffffff&primaryColor=%23178af6ff";
      }, 800);
    },
  },
};
</script>

<style scoped>
#preloader {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 9999;
  background: white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.header_bottom {
  background-color: transparent;
}

#preloader img {
  max-width: 300px; /* Adjust size of the pre-loader image */
  animation: wobble 1s ease-in-out infinite; /* Animation properties */
}

@keyframes wobble {
  0% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(3deg);
  }
  50% {
    transform: rotate(-3deg);
  }
  75% {
    transform: rotate(2deg);
  }
  100% {
    transform: rotate(0deg);
  }
}

/* Pre-loader styles */

/* Add dropdown styling */
.navbar-nav .dropdown-menu {
  background-color: black;
  border: none;
  border-radius: 0;
  text-align: center; /* Center text */
  margin-top: 0; /* Adjust as needed */
  font-size: 14px;
}

/* Dropdown item styling */
.navbar-nav .dropdown-item {
  color: #fff; /* White text color */
  font-size: 14px; /* Adjust font size as needed */
}

/* Dropdown item hover effect */
.navbar-nav .dropdown-item:hover {
  background-color: rgba(
    0,
    230,
    184,
    0.1
  ); /* Light background color on hover */
  color: #00e6b8; /* Text color on hover */
}

/* Override bootstrap default toggler icon color */
.navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='rgba(0, 255, 204, 0.5)' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 7h22M4 15h22M4 23h22'/%3E%3C/svg%3E");
}

/* Navbar link colors */
.navbar-nav .nav-link {
  color: #00ffcc;
}

.navbar-nav .nav-link:hover,
.navbar-nav .nav-link:focus {
  color: #00e6b8;
}
</style>
