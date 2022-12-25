<template>
  <div class="project-card">
    <div class="video-box">
      <video
        :src="require('@/assets/' + project.src + '')"
        autoplay
        loop
        muted
      ></video>
    </div>
    <!-- <div class="img-box">
      <img :src="require('@/assets/' + project.src + '')" />
    </div> -->
    <div class="inner-box">
      <h3 :style="{ color: this.project.mainColor }">
        {{ this.project.name }}
      </h3>
      <div class="span-box">
        <span v-if="project.client">CLIENT: {{ project.client }}</span>
        <span v-if="project.server">SERVER: {{ project.server }}</span>
      </div>
      <div class="a-box">
        <Atag
          text="View Demo"
          :href="project.demo"
          :background="project.mainColor"
          color="#fff"
          :borderColor="project.mainColor"
        />
        <Atag
          text="View Code"
          :href="project.code"
          background="transparent"
          :color="project.mainColor"
          :borderColor="project.mainColor"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Atag from "./Atag";
export default {
  name: "ProjectCard",
  props: {
    project: {
      name: String,
      src: String,
      demo: String,
      code: String,
      mainColor: String,
    },
  },
  components: { Atag },
};
</script>

<style scoped>
.project-card {
  position: relative;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.project-card::before {
  content: "";
  width: 100%;
  height: 100%;
  position: absolute;
  transform: scale(0);
  background-color: rgba(51, 51, 51, 0.75);
  transition: 0.3s;
}

.project-card:hover::before {
  transform: scale(1);
}

.inner-box {
  width: 94%;
  height: 90%;
  background-color: rgba(51, 51, 51, 0.85);
  transform: scale(0);
  position: absolute;
  transition: 0.3s;
  transition-delay: 0.1s;
  display: flex;
  gap: 10px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px solid #cecece;
}

.project-card:hover > .inner-box {
  transform: scale(1);
}

.img-box,
.video-box {
  width: 100%;
}

video {
  width: 100%;
  aspect-ratio: 16/9;
}

video:focus {
  outline: transparent;
}

img {
  width: 100%;
  aspect-ratio: 16/9;
}

.span-box {
  display: flex;
  flex-direction: column;
  margin-bottom: 10px;
}

span {
  color: #fff;
}

h3 {
  font-weight: 500;
}

span {
  font-weight: 500;
  font-size: 11px;
  letter-spacing: 1.6px;
}
</style>
