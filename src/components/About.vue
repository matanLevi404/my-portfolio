<template>
  <section id="about" class="about-section">
    <div class="container">
      <h3 class="title">About.</h3>
      <div class="about-area">
        <div class="col-left">
          <h2>
            I'm a
            <strong
              ><span class="color-inject">Full Stack</span> Developer</strong
            >
            from Israel, Who loves coding .
          </h2>
          <p>
            I am a 24yo Full stack web developer with ability to learn and
            collaborate in rapidly changing environments and compositions.
            Worked through 1000+ hours of John Bryce bootcamp & self study,
            learning JavaScript, React, Angular, Vue, Node.Js, Express, MySQL,
            SQL, MongoDB. Eager to tackle web development/design challenges to
            achieve lasting impacts on user experience.
          </p>
          <Button
            @click="scrollToProjects()"
            text="View Work"
            color="#333"
            background="transparent"
            hoverColor="#000"
            hoverBackground="#f7f7f7"
            borderColor="#cecece"
            hoverBorderColor="#333"
            borderPx="1px"
            borderRadius="25px"
          />
        </div>
        <div class="col-right">
          <video autoplay loop>
            <source src="@/assets/svg.mp4" />
          </video>
          <!-- <img src="@/assets/about-image.png" alt="" /> -->
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Button from "./Button";

export default {
  name: "About",
  components: { Button },
  methods: {
    scrollToProjects() {
      document.getElementById("projects").scrollIntoView({
        behavior: "smooth",
      });
    },
  },
};
</script>

<style scoped>
.about-section {
  padding: 80px 0;
}

.about-area {
  display: flex;
}

.col-left {
  width: 50%;
}

h2 {
  font-size: 30px;
  font-weight: 400;
  line-height: 45px;
  margin-bottom: 15px;
  color: #333;
}

p {
  line-height: 28px;
  margin-bottom: 25px;
}

.col-right {
  width: 50%;
  display: flex;
  justify-content: center;
}

img,
video {
  width: 75%;
}

@media (max-width: 992px) {
  .about-area {
    flex-direction: column;
    text-align: center;
  }

  .col-left h2 {
    font-size: 22px;
  }

  .col-left,
  .col-right {
    width: 100%;
  }

  .title {
    font-size: 35px;
  }
}

@media (max-width: 767px) {
  .col-left {
    text-align: left;
  }
  .col-left h2 {
    font-size: 20px;
    line-height: 30px;
  }
}
</style>
