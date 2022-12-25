<template>
  <div>
    <!-- <Navbar /> -->
    <Header />
    <About />
    <Skills />
    <Projects />
    <!-- <ContactBand /> -->
    <!-- <Contact /> -->
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import Header from "./components/Header";
import About from "./components/About";
import Skills from "./components/Skills";
import Projects from "./components/Projects";
import Contact from "./components/Contact";
import ContactBand from "./components/ContactBand";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: {
    Navbar,
    Header,
    About,
    Skills,
    Projects,
    Contact,
    ContactBand,
    Footer,
  },
  methods: {},
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
  transition: 0.3s;
}

div {
  align-items: center;
}

.section {
  min-height: 100vh;
}

.container {
  width: 100%;
  margin: 0 auto;
  padding: 0px 12px;
  /* border: 1px solid red; */
}

ul {
  list-style: none;
  display: flex;
}

.title {
  font-size: 50px;
  text-transform: capitalize;
  font-weight: 900;
  margin-top: 0;
  color: #101010;
  text-align: center;
  margin-bottom: 60px;
  letter-spacing: 1.6px;
}

p {
  font-size: 16px;
  font-weight: 300;
  color: #333;
}

a {
  text-decoration: none;
}

.color-inject {
  color: #18cbbe;
}

@media (min-width: 1200px) {
  .container {
    max-width: 1142px;
  }
}

@media (min-width: 993px) and (max-width: 1199px) {
  .container {
    max-width: 962px;
  }
}

@media (min-width: 768px) and (max-width: 992px) {
  .container {
    max-width: 722px;
  }

  .heading {
    font-size: 35px;
    line-height: 45px;
  }

  .about-area {
    flex-direction: column;
  }

  .about-area .col-left,
  .about-area .col-right {
    width: 100%;
  }
}

@media (min-width: 576px) and (max-width: 767px) {
  .container {
    max-width: 542px;
  }
}
</style>
