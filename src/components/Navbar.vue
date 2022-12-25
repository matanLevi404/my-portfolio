<template>
  <div
    ref="navbar"
    class="navbar-area"
    :class="{ scrolled: scrolled }"
    v-motion
  >
    <div class="container">
      <div class="navbar">
        <h3 :class="{ scrolled: scrolled }">Matan.</h3>
        <Menu :menuType="'visible'" :isOpen="isOpen" />
        <Burger @toggle-menu="toggleMenu" />
        <Menu :menuType="'hidden'" :isOpen="isOpen" />
      </div>
    </div>
  </div>
</template>

<script>
import Menu from "./Menu";
import Burger from "./Burger";

export default {
  name: "Navbar",
  data() {
    return {
      menuType: "visible",
      isOpen: false,
      scrolled: false,
    };
  },
  components: { Menu, Burger },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
    click() {
      console.log(this.scrolled);
    },
  },
};
</script>

<style scoped>
.navbar-area {
  width: 100%;
  position: fixed;
  padding: 15px 0px;
  z-index: 999;
}

.navbar {
  border: 1px solid green;
  display: flex;
  position: relative;
  justify-content: space-between;
  padding: 8px 0px;
}

h3 {
  transition: all 0.3s ease-out 0s;
  font-size: 30px;
  color: #fff;
  text-transform: capitalize;
  letter-spacing: 1px;
  font-weight: 800;
}

h3.scrolled {
  color: #333;
}

.navbar-area.scrolled {
  background-color: #fff;
  color: #333;
  padding: 0;
}
</style>
