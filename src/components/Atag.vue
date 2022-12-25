<template>
  <a :style="style" :href="href" target="_blank">{{ this.style.text }} </a>
</template>

<script>
export default {
  name: "Atag",
  props: {
    href: String,
    text: String,
    background: String,
    color: String,
    borderColor: String,
  },
  data() {
    return {
      style: {
        text: this.text,
        "--background": this.background,
        "--color": this.color,
        "--borderColor": this.borderColor,
      },
    };
  },
};
</script>

<style scoped>
a {
  color: var(--color);
  background-color: var(--background);
  width: 120px;
  font-size: 13px;
  margin: 10px 0px;
  padding: 8px 21px;
  border: 2px solid var(--borderColor);
  margin: 0 5px;
}

a:hover {
  background-color: var(--borderColor);
  color: #fff;
}
</style>
