<template>
  <section id="skills" class="skills-section">
    <div class="container">
      <h2 class="title">Skills.</h2>
      <div class="skills">
        <SkillCard
          v-for="skill in skills"
          :skill="skill"
          :key="skill.heading"
        />
      </div>
    </div>
  </section>
</template>

<script>
import SkillCard from "./SkillCard";

export default {
  name: "Skills",
  components: { SkillCard },
  data() {
    return {
      skills: [
        {
          img: "angular-logo.png",
          heading: "Angular",
          text: "",
        },
        {
          img: "vue-logo.png",
          heading: "Vue",
          text: "",
        },
        {
          img: "react-logo.png",
          heading: "React",
          text: "",
        },
        {
          img: "node-logo.png",
          heading: "Node.js",
          text: "",
        },
        {
          img: "mongo-logo.png",
          heading: "mongoDB",
          text: "",
        },
        {
          img: "sql-logo.png",
          heading: "MySQL",
          text: "",
        },
      ],
    };
  },
};
</script>

<style scoped>
.skills-section {
  padding: 80px 0px;
  /* background-color: #f7f7f7; */
  background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("@/assets/cta-bg.jpg");
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}

.skills {
  /* border: 1px solid green; */
  display: flex;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
  gap: 24px;
}

h2 {
  color: #fff;
}

@media (max-width: 992px) {
  .skills {
    grid-template-columns: 1fr 1fr 1fr;
  }

  h2 {
    font-size: 35px;
  }
}

@media (max-width: 576px) {
  .skills {
    grid-template-columns: 1fr 1fr;
  }
}
</style>
