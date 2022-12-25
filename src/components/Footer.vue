<template>
  <footer class="footer-section">
    <div class="container">
      <ul class="footer-list">
        <li>
          <h2>Matan.</h2>
        </li>
        <li>
          <!-- <p>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nulla, a
            sint. Odio blanditiis reiciendis rem, dolorum quia laborum optio
            dolor numquam inventore, vitae perferendis, laboriosam enim
            perspiciatis cupiditate soluta. Libero.
          </p> -->
        </li>
      </ul>
    </div>
  </footer>
</template>

<script>
import MediaLinks from "./MediaLinks";

export default {
  name: "Footer",
  components: { MediaLinks },
};
</script>

<style scoped>
.footer-section {
  padding: 80px 0px;
  background-color: #1b1b1b;
  color: #fff;
  text-align: center;
}

.footer-list {
  width: 75%;
  padding: 0px 50px;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  position: relative;
}

.container {
  position: relative;
}

.container::before {
  content: "";
  display: block;
  position: absolute;
  width: 100%;
  height: 1px;
  left: 0;
  bottom: 0;
  background-color: #333;
}

.container::after {
  content: "Matan © 2023 All Right Resived";
  display: block;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  padding: 20px 0px;
  font-weight: 200;
}

.footer-list li {
  margin: 0px auto 20px auto;
}

p {
  color: #fff;
  line-height: 26px;
  font-weight: 200;
}
</style>
