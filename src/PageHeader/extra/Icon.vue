<template>
  <svg
    viewBox="0 0 24 24"
    class="icon"
    :style="`fill: ${color}`"
  >
    <path :d="path" />
  </svg>
</template>

<script>
import icons from "./icons.json"
export default {
  name: "Icon",
  props: {
    name: {
      type: String,
      default: "back1"
    },
    size: {
      type: String,
      default: "5em"
    },
    color: {
      type: String,
      default: "#000"
    }
  },
  computed: {
    path() {
      return icons[this.name]
    },
    styleClasses() {
      return [this.size].map(val => val && `is-${val}`);
    }
  }
}
</script>
<style>
/* default style */
.icon {
  width: 1.2em;
  height: 1.2em;
  fill: #000;
}

/* sizes */
.icon.is-large {
  width: 2em;
  height: 2em;
}
.icon.is-medium {
  width: 1.6em;
  height: 1.6em;
}
.icon.is-normal {
  width: 1.2em;
  height: 1.2em;
}
.icon.is-small {
  width: 1em;
  height: 1em;
}
.icon.is-tiny {
  width: 0.8em;
  height: 0.8em;
}
</style>