<template>
  <button :class="[styleType]" @click.prevent="clickEvent">{{ text }}</button>
</template>
<script>
export default {
  props: {
    clickEvent: {
      type: Function,
    },
    text: {
      type: String,
      default: "",
    },
    styleType: {
      type: String,
      defalut: "blue",
    },
  },
};
</script>
<style lang="scss">
button {
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 29px;
  padding: 1.25em 2em;
  background-color: #fefefe;
  position: relative;
  cursor: pointer;
  outline: none;
  text-decoration: none;
  font-size: inherit;
  line-height: 1.6;
  font-family: inherit;
  font-weight: 600;
  color: #382b22;
  border: 2px solid #8599b1;
  border-radius: 0.75em;
  transform-style: preserve-3d;
  user-select: none;
  transition: transform 0.15s ease-out, background-color 0.15s ease-out;
  &::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    background: #c4d8f9;
    border-radius: inherit;
    box-shadow: 0 0 0 2px #8599b1, 0 0.625em 0 0 #e2efff;
    transform: translate3d(0, 0.75em, -1em);
    transition: transform 0.15s ease-out, box-shadow 0.15s ease-out;
  }
  &:hover {
    transform: translateY(0.25em);
  }
  &.pink {
    display: inline-block;
    width: 300px;
    padding: 1.25em 2em;
    margin-bottom: 30px;
    border-color: #b18597;
    background: #fff0f0;
    &::before {
      background: #f9c4d2;
      box-shadow: 0 0 0 2px #b18597, 0 0.625em 0 0 #ffe3e2;
    }
  }
}
</style>
