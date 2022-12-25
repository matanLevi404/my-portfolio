<template>
  <section id="projects" class="projects-section">
    <div class="container">
      <h2 class="title">Projects.</h2>
      <div class="projects">
        <ProjectCard
          v-for="(project, index) in projects"
          :key="project.name"
          :project="project"
          :index="index"
        />
      </div>
    </div>
  </section>
</template>

<script>
import ProjectCard from "./ProjectCard";
export default {
  name: "Projects",
  components: { ProjectCard },
  data() {
    return {
      projects: [
        {
          name: "Kicks",
          src: "kicks.mp4",
          demo: "https://kicks-client.vercel.app/",
          mainColor: "#d40317",
          client: "Angular, Css, Material, Stripe",
          server: "Node.js, Express, jwt, MongoDB",
        },
        {
          name: "Path Visualizer",
          src: "path.mp4",
          demo: "https://path-visualizer-brown.vercel.app/",
          code: "https://github.com/matanLevi404/path-visualizer",
          mainColor: "#1abc9c",
          client: "Angular, Css/Scss, Material",
        },
        {
          name: "Sort Visualizer",
          src: "sort.mp4",
          demo: "https://sort-visualizer-kappa.vercel.app/",
          code: "https://github.com/matanLevi404/sort-visualizer",
          mainColor: "#1A2027",
          client: "React, Css/Scss, Material",
        },
        {
          name: "Cryptonite",
          src: "Cryptonite.mp4",
          demo: "https://cryptonite-delta.vercel.app/",
          code: "https://github.com/matanLevi404/Cryptonite",
          mainColor: "#1a73e8",
          client: "Jquery, Css",
        },
      ],
    };
  },
};
</script>

<style scoped>
.projects-section {
  padding: 80px 0px;
  background-color: #f7f7f7;
}

.projects {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
}

@media (max-width: 992px) {
  h2 {
    font-size: 35px;
  }
}

@media (max-width: 767px) {
  .projects {
    grid-template-columns: 1fr;
  }
}
</style>
