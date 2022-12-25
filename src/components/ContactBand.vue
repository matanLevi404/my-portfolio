<template>
  <div class="band">
    <div class="container">
      <ul class="contact-list">
        <li><font-awesome-icon icon="fa-regular fa-phone" /></li>
        <li><font-awesome-icon icon="fa-regular fa-phone" /></li>
        <li><font-awesome-icon icon="fa-regular fa-phone" /></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactBand",
};
</script>

<style scoped>
.band {
  padding: 120px 0px;
  background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("@/assets/cta-bg.jpg");
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}

.contact-band {
  margin: auto;
  color: #fff;
}

li {
  color: #fff;
}
</style>
