<template>
  <ul
    :class="{
      'visible-menu': menuType == 'visible' ? true : false,
      'hidden-menu': menuType == 'visible' ? false : true,
      open: isOpen,
      scrolled: scrolled,
    }"
  >
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li>
      <a href="#projects"><span class="color-inject">Projects</span></a>
    </li>
    <!-- <li><a href="#contact">Contact</a></li> -->
  </ul>
</template>

<script>
export default {
  name: "Menu",
  props: {
    menuType: String,
    isOpen: Boolean,
    scrolled: true,
  },
  mounted() {
    document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
      anchor.addEventListener("click", function (e) {
        e.preventDefault();

        document.querySelector(this.getAttribute("href")).scrollIntoView({
          behavior: "smooth",
        });
      });
    });
  },
};
</script>

<style scoped>
.visible-menu {
  color: #fff;
}

.visible-menu li {
  margin-left: 40px;
  font-size: 16px;
  font-weight: 500;
  color: #eee;
  -webkit-transition: all 0.3s ease-out 0s;
  transition: all 0.3s ease-out 0s;
  position: relative;
  text-transform: capitalize;
}

.visible-menu li a {
  color: #eee;
}

.visible-menu.scrolled li a {
  color: #333;
}

.visible-menu li:hover {
  cursor: pointer;
}

.visible-menu li::before,
.visible-menu.scrolled li::before {
  content: "";
  height: 2px;
  width: 0;
  position: absolute;
  top: 110%;
  transition: 0.3s;
}

.visible-menu li::before {
  background-color: #fff;
}

.visible-menu.scrolled li::before {
  background-color: #333;
}

.visible-menu li:hover::before,
.visible-menu.scrolled li:hover::before {
  width: 100%;
}

.hidden-menu {
  width: 100%;
  /* border: 1px solid green; */
  position: absolute;
  top: 100%;
  flex-direction: column;
  gap: 10px;
  padding: 12px;
  transform: scaleY(0);
  transition: 0.3s;
  transform-origin: top;
  background-color: #fff;
  border-radius: 10px;
  border-top-left-radius: 0;
  border-top-right-radius: 0;
}

.hidden-menu.open {
  transform: scaleY(1);
}

.hidden-menu li {
  padding: 10px;
  border: 1px solid #eee;
  border-radius: 4px;
  font-size: 13px;
  font-weight: 500;
}

.hidden-menu li a {
  color: #081828;
  width: 100%;
  display: block;
  height: 100%;
}

.hidden-menu li:hover {
  background-color: #333;
  cursor: pointer;
}

.hidden-menu li:hover a {
  color: #fff;
}

@media (max-width: 992px) {
  .visible-menu {
    display: none;
  }
}

@media (min-width: 992px) {
  .hidden-menu {
    display: none;
  }
}
</style>
