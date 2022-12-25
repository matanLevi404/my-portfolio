<template>
  <div
    class="skill-card"
    v-motion
    :initial="{ opacity: 0, y: 100 }"
    :visible="{ opacity: 1, y: 0 }"
    :delay="index * 1000"
  >
    <div class="content-box">
      <div class="img-box">
        <img :src="require('@/assets/' + skill.img + '')" alt="" />
      </div>
      <h4>{{ skill.heading }}</h4>
      <p>
        <!-- Lorem ipsum, dolor sit amet consectetur adipisicing elit. Facere libero
        nisi mollitia vel eos pariatur cum sed, soluta fuga consequuntur id -->
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "SkillCard",
  props: {
    skill: {
      img: String,
      heading: String,
      text: String,
      index: Number,
    },
  },
};
</script>

<style scoped>
.skill-card {
  /* border: 1px solid #e1ebf7;s */
  border-radius: 6px;
  position: relative;
  overflow: hidden;
  z-index: 2;
}
/* 
.skill-card::before {
  content: "";
  width: 100%;
  height: 100%;
  position: absolute;
  background-color: #fff;
  z-index: -1;
  transform: scaleY(0);
  transform-origin: bottom;
  transition: 0.3s ease-in;
}

.skill-card:hover::before {
  transform: scaleY(1);
} */

.content-box {
  /* padding: 61px 22px; */
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.img-box {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

img {
  margin-top: 1px;
  width: 80%;
  z-index: 5;
}

h4 {
  margin: 20px 0px;
  color: #fff;
}

p {
  text-align: center;
  line-height: 28px;
}

@media (max-width: 992px) {
  .img-box {
    width: 80px;
    height: 80px;
  }
}
</style>
