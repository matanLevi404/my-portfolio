<template>
  <ul class="media-icons">
    <li>
      <a
        href="https://wa.me/+972527099594"
        target="_blank"
        id="whatsapp"
        :class="{ scrolled: !scrolled }"
      >
        <font-awesome-icon icon="fa-brands fa-square-whatsapp" />
      </a>
    </li>
    <li>
      <a
        href="https://www.linkedin.com/in/matanlevi404/"
        target="_blank"
        id="linkedin"
        :class="{ scrolled: !scrolled }"
      >
        <font-awesome-icon icon="fa-brands fa-linkedin" />
      </a>
    </li>
    <li>
      <a
        href="https://github.com/matanLevi404?tab=repositories"
        target="_blank"
        id="github"
        :class="{ scrolled: !scrolled }"
      >
        <font-awesome-icon icon="fa-brands fa-square-github" />
      </a>
    </li>
  </ul>
</template>

<script>
export default {
  name: "MediaLinks",
  props: { scrolled: Boolean },
};
</script>

<style scoped>
.media-icons {
  display: flex;
  padding: 5px 0px;
  left: 0;
}

.svg-inline--fa {
  font-size: 2.5em;
  margin-right: 10px;
}

a {
  color: #000;
  transition-property: none;
}

/* a#whatsapp:hover {
  color: #128c7e;
}

a#linkedin:hover {
  color: #0a66c2;
} */

a.scrolled {
  color: #fff;
}

@media (max-width: 767px) {
  .svg-inline--fa {
    font-size: 2em !important;
  }
}
</style>
