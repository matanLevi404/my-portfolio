<template>
  <button :style="this.style">{{ this.style.text }}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    action: String,
    color: String,
    hoverColor: String,
    background: String,
    hoverBackground: String,
    borderColor: String,
    hoverBorderColor: String,
    borderPx: String,
    borderRadius: String,
  },
  data() {
    return {
      style: {
        text: this.text,
        "--color": this.color,
        "--background": this.background,
        "--borderColor": this.borderColor,
        "--hoverBorderColor": this.hoverBorderColor,
        "--hoverColor": this.hoverColor,
        "--hoverBackground": this.hoverBackground,
        "--borderPx": this.borderPx,
        "--borderRadius": this.borderRadius,
      },
    };
  },
};
</script>

<style scoped>
button {
  padding: 10px 25px;
  border-radius: var(--borderRadius);
  font-size: 16px;
  letter-spacing: 1px;
  font-weight: 300;
  min-width: 160px;
  background-color: var(--background);
  border: var(--borderPx) solid var(--borderColor);
  color: var(--color);
}

button:hover {
  cursor: pointer;
  color: var(--hoverColor);
  background-color: var(--hoverBackground);
  border: var(--borderPx) solid var(--hoverBorderColor);
}
</style>
