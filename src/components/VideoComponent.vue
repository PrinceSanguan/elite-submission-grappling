<template>
  <section class="video_section layout_padding">
    <div class="container">
      <div class="row">
        <div class="col-md-8 offset-md-2">
          <div class="video-box">
            <!-- Main Video Thumbnail and Popup -->
            <div class="video-item main-video">
              <h2>Start your martial arts journey!</h2>
              <p class="video-description">
                Listen to coach Ethan in the short video below as he talks you
                through some of the areas we pride ourselves in!
              </p>
              <div class="video-container">
                <img
                  src="{{ asset('thumbnails/main-video-thumbnail.webp') }}"
                  alt="Main Video Thumbnail"
                  class="thumbnail-image main-thumbnail"
                />
                <button class="play-button" aria-label="Play"></button>
                <video controls class="video-element main-video-element">
                  <source
                    src="{{asset('videos/video1.mp4')}}"
                    type="video/mp4"
                  />
                  Your browser does not support the video tag.
                </video>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.video_section {
  padding: 60px 0;
  position: relative;
  background-color: #ffffff;
  color: #0b0a0a;
  overflow: hidden; /* Ensure the moving background does not overflow */
}

.video_section::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%; /* Make the background twice the width */
  height: 100%;
  /*   background-image: url("/images/background1.webp"); */
  background-size: cover;
  background-repeat: repeat-x; /* Repeat the background horizontally */
  background-position: 0 0;
  filter: brightness(30%);
}

.video-box {
  display: flex;
  justify-content: center;
  flex-direction: column; /* Align items in a column */
  align-items: center; /* Center align horizontally */
}

.video-item {
  text-align: center;
  margin-bottom: 20px;
}

.video-item h2 {
  font-size: 3rem;
  margin-bottom: 10px;
  font-weight: bold;
  color: #00ffcc;
}

.video-item p {
  font-size: 1rem;
  font-weight: bold;
  color: #00ffcc;
}

.video-description {
  font-size: 18px;
  margin-bottom: 20px;
}

.video-container {
  position: relative;
  cursor: pointer;
  text-align: center;
}

.thumbnail-image {
  display: inline-block;
  max-width: 100%;
  height: auto;
  border-radius: 10px;
}

.play-button {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 80px;
  height: 80px;
  background-color: rgba(0, 0, 0, 0.6);
  border: none;
  border-radius: 50%;
  cursor: pointer;
  outline: none;
  z-index: 2;
  transition: background-color 0.3s ease;
}

.play-button::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-40%, -50%);
  width: 0;
  height: 0;
  border-left: 32px solid white;
  border-top: 20px solid transparent;
  border-bottom: 20px solid transparent;
}

.play-button:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* Added to ensure landscape mode */
.video-element {
  object-fit: contain; /* Ensure video fits container */
  width: 100%; /* Ensure video takes full width */
  height: auto; /* Allow height to adjust */
  max-height: 100vh; /* Limit height to viewport height */
  max-width: 100%; /* Limit width to viewport width */
}

@media (max-width: 768px) {
  .video_section::before {
    width: 400%;
  }

  .video-item {
    text-align: center;
  }

  .video_section::before {
    animation: moveBackground 20s linear infinite;
  }
}

/* Keyframes for background animation */
@keyframes moveBackground {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-50%);
  }
}
</style>

<script>
export default {
  name: "VideoComponent",

  mounted() {
    document.addEventListener("DOMContentLoaded", function () {
      const mainVideo = document.querySelector(".main-video-element");
      const mainThumbnail = document.querySelector(".main-thumbnail");
      const playButton = document.querySelector(".play-button");

      // Initially hide the main video element
      mainVideo.style.display = "none";

      playButton.addEventListener("click", function () {
        if (mainVideo.paused) {
          mainVideo.play();
          mainVideo.style.display = "block"; // Show the main video element
          mainThumbnail.style.display = "none"; // Hide the main thumbnail
          mainVideo.classList.add("landscape-mode"); // Optional: Add a class for styling purposes
        } else {
          mainVideo.pause();
        }
      });

      mainVideo.addEventListener("pause", function () {
        mainVideo.style.display = "none"; // Hide the main video element when paused
        mainThumbnail.style.display = "block"; // Show the main thumbnail
        mainVideo.classList.remove("landscape-mode"); // Optional: Remove landscape mode class
      });

      // Optional: Click on thumbnail to play in landscape mode
      mainThumbnail.addEventListener("click", function () {
        mainVideo.style.objectFit = "contain"; // Ensure video fits container
      });
    });
  },
};
</script>
