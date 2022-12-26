<template>
  <div>
    <div
      ref="navbar"
      class="navbar-area"
      :class="{ scrolled: scrolled }"
      v-motion
    >
      <div class="container">
        <div class="navbar">
          <MediaLinks :scrolled="scrolled" />

          <!-- <h3 :class="{ scrolled: scrolled }">
            Matan.
          </h3> -->

          <Menu :menuType="'visible'" :isOpen="isOpen" :scrolled="scrolled" />
          <Burger @toggle-menu="toggleMenu" />
          <Menu :menuType="'hidden'" :isOpen="isOpen" />
        </div>
      </div>
    </div>
    <header ref="header" class="header-section section">
      <div class="container">
        <ul class="heading-menu">
          <li ref="heading" class="heading">
            Hi, I <span class="color-inject">Am</span> Matan Levi
          </li>
          <li class="sub-heading">Full Stack Web Developer</li>
          <li>
            <Button
              @click="downloadCV()"
              text="Download CV"
              color="#18cbbe"
              background="transparent"
              borderColor="#18cbbe"
              hoverColor="#000"
              hoverBackground="#fff"
              hoverBorderColor="#fff"
              borderPx="2px"
              borderRadius="25px"
            />
          </li>
        </ul>
      </div>
    </header>
  </div>
</template>

<script>
import Button from "./Button";
import Menu from "./Menu";
import Burger from "./Burger";
import MediaLinks from "./MediaLinks";

export default {
  name: "Header",
  data() {
    return {
      menuType: "visible",
      isOpen: false,
      scrolled: false,
    };
  },
  components: { Button, Menu, Burger, MediaLinks },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
    click() {
      console.log(this.scrolled);
    },
    downloadCV() {
      const file = require("@/assets/MatanLevi_CV.pdf");

      const linkSource = file.default;
      const downloadLink = document.createElement("a");
      const fileName = "MatanLevi_CV.pdf";
      downloadLink.href = linkSource;
      downloadLink.download = fileName;
      downloadLink.click();

      document.body.removeChild(downloadLink);
    },
  },
  mounted() {
    console.log(this.$refs.navbar, this.$refs.heading);
    const observer = new IntersectionObserver(
      (enteries) => {
        enteries.forEach((entery) => {
          if (!entery.isIntersecting) this.scrolled = true;
          else this.scrolled = false;
        });
      },
      { threshold: 1 }
    );
    observer.observe(this.$refs.heading);
  },
};
</script>

<style scoped>
.header-section {
  background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("@/assets/header-img2.jpg");
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  display: flex;
  align-items: center;
}

.heading-menu {
  /* border: 1px solid green; */
  color: #fff;
  flex-direction: column;
  gap: 10px;
}

ul li {
  text-align: center;
}

.heading {
  font-size: 80px;
  font-weight: 700;
  line-height: 92px;
  text-transform: capitalize;
  letter-spacing: 3px;
  color: #fff;
  padding-top: 65.333px;
}

.sub-heading {
  font-size: 30px;
  line-height: 45px;
  letter-spacing: 1px;
  margin-top: 0px;
  margin-bottom: 15px;
  text-transform: capitalize;
  font-weight: 500;
  color: #fefefe;
  letter-spacing: 1.6px;
}

/* NAVBAR */
.navbar-area {
  width: 100%;
  position: fixed;
  padding: 15px 0px;
  z-index: 999;
}

.navbar {
  /* border: 1px solid green; */
  display: flex;
  position: relative;
  justify-content: space-between;
  padding: 8px 0px;
}

h3 {
  transition: all 0.3s ease-out 0s;
  font-size: 30px;
  position: relative;
  color: #fff;
  text-transform: capitalize;
  letter-spacing: 1px;
  font-weight: 800;
}

h3.scrolled {
  color: #161616;
}

.navbar-area.scrolled {
  background-color: #fff;
  color: #161616;
  padding: 0;
  box-shadow: rgb(33 35 38 / 15%) 0px 10px 10px -10px;
}

.container {
  position: relative;
}

/* NAVBAR */

@media (max-width: 992px) {
  .heading {
    font-size: 35px;
    line-height: 45px;
  }

  .sub-heading {
    font-size: 22px;
    line-height: 32px;
  }
}

@media (max-width: 767px) {
  .heading {
    font-size: 25px;
    line-height: 45px;
  }

  .sub-heading {
    font-size: 18px;
    line-height: 32px;
  }
}
</style>
