<template>
  <div class="home">
    <nav class="d-flex">
      <div class="logo">
        <img src="../assets/img/psikologicare.png" alt="logo" />
        <h4>PT. Care Indonesia Solusi</h4>
      </div>
      <div class="navigate d-flex">
        <h6>Home</h6>
        <a href="#Service"><h6>Service</h6></a>
        <h6>Training</h6>
        <h6>Gallery</h6>
        <h6>Article</h6>
        <h6>About</h6>
      </div>
    </nav>
    <header class="head">
      <div class="d-flex">
        <div class="intro">
          <b><h1>Online Assesment</h1></b>
          <p>
            The smartest way to get your potential <br />
            candicate
          </p>
        </div>
        <div class="cover">
          <img src="../assets/img/undraw_work_chat_erdt.svg" alt="" />
        </div>
      </div>
    </header>
    <section class="our-service" id="Service">
      <section class="title d-flex justify-content-center">
        <h3 class="mt-3">Our Service</h3>
      </section>
      <carousel :perPage="3">
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/checklist.png" alt="thumb" />
            <p><b>Psycometric Test Tools Development</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/recruitment.png" alt="thumb" />
            <p><b>Assessment Center & Competency</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/analytics.png" alt="thumb" />
            <p><b>Online Assessment</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/computer-monitor.png" alt="thumb" />
            <p><b>Recruitment, Selection & Promotion</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/employee.png" alt="thumb" />
            <p><b>Executive Search (Head Hunter)</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/exam.png" alt="thumb" />
            <p><b>Online Psycho test Service</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/personal-development.png" alt="thumb" />
            <p><b>Training & People Development</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/web.png" alt="thumb" />
            <p><b>Survey & Diagnostics Studies</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="service-card">
            <img src="../assets/img/qualitative-research.png" alt="thumb" />
            <p><b>HR Policy, Strategy & Business Solutions</b></p>
          </section>
        </slide>
      </carousel>
    </section>
    <section class="why-bina">
      <section class="title d-flex justify-content-center">
        <h3 class="mt-5">Why Binakarir?</h3>
      </section>
      <carousel :perPage="3">
        <slide class="slide">
          <section class="small-card">
            <img src="../assets/img/honesty.png" alt="thumb" />
            <p><b>Trusted</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="small-card">
            <img src="../assets/img/tick.png" alt="thumb" />
            <p><b>Relevan</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="small-card">
            <img src="../assets/img/certified.png" alt="thumb" />
            <p><b>Certified</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="small-card">
            <img src="../assets/img/return.png" alt="thumb" />
            <p><b>Reach Many Places</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="small-card">
            <img src="../assets/img/clock.png" alt="thumb" />
            <p><b>Easy To Access</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="small-card">
            <img src="../assets/img/timer.png" alt="thumb" />
            <p><b>Fast</b></p>
          </section>
        </slide>
        <slide class="slide">
          <section class="small-card">
            <img src="../assets/img/certified.png" alt="thumb" />
            <p><b>Realtime</b></p>
          </section>
        </slide>
      </carousel>
      <section class="p-5">
        <fold></fold>
      </section>
    </section>
  </div>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";

export default {
  name: "Home",
  components: {
    Carousel,
    Slide
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const nav = document.querySelector("nav");
      nav.classList.toggle("sticky", window.scrollY > 0);
    }
  }
};
</script>
<style scoped>
.home {
  background: #f5f8fc;
}
.head {
  position: relative;
  height: 100vh;
  background: #f0ddd8;
  clip-path: polygon(0 0, 100% 0, 100% 89%, 0% 100%);
}
nav {
  position: fixed;
  width: 100%;
  height: 80px;
  z-index: 2;
  transition: 0.6s;
}
.sticky {
  background: #ffffff;
}
.intro {
  display: flex;
  margin-top: 80px;
  flex-direction: column;
  justify-content: center;
  width: 50%;
  padding: 20px;
  box-sizing: border-box;
  margin-top: 80px;
}
.intro h1 {
  font-size: 70px;
}
.intro p {
  font-size: 20px;
}
.cover {
  margin-top: 80px;
  width: 50%;
  height: 100%;
  padding: 10px;
  box-sizing: border-box;
}
.cover img {
  width: 100%;
  /* height: 100%; */
}
.logo {
  width: 50%;
  display: flex;
  align-items: center;
  padding: 10px;
  color: #d94e82;
}
.logo img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  margin-right: 20px;
}
.navigate {
  padding: 20px;
  align-items: center;
  width: 50%;
  justify-content: space-around;
}
.navigate h6 {
  cursor: pointer;
  color: black;
  text-decoration: none;
}
.navigate h6:hover {
  color: #d94e82;
}
.why-bina {
  height: 100vh;
  background: #f0ddd8;
  clip-path: polygon(0 8%, 100% 0, 100% 100%, 0 100%);
}
.service-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 200px;
  height: 200px;
  text-align: center;
  transition: 0.2s;
  /* border-radius: 8px; */
  cursor: pointer;
}
.service-card:hover {
  background: #f0ddd8;
  transition: 0.2s;
  transform: scale(1.1);
}
.service-card img {
  width: 100px;
  height: 100px;
}
.small-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 150px;
  height: 150px;
  text-align: center;
  transition: 0.2s;
  border-radius: 8px;
  cursor: pointer;
}
.small-card:hover {
  background: #f5f8fc;
  transition: 0.2s;
  transform: scale(1.2);
}
.small-card img {
  width: 80px;
  height: 80px;
}
.slide {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 230px;
}
.btn-anu {
  height: 48px;
  width: 150px;
  background: linear-gradient(270deg, #a800ca 0%, #6d01d3 100%);
  border-radius: 8px;
  color: white;
  margin-top: 20px;
  border: none;
  transition: 0.5s;
}
.btn-anu:hover {
  background: linear-gradient(270deg, #8702a1 0%, #4e0197 100%);
  transition-delay: 1s;
}
</style>
