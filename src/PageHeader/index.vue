<template>
  <div class="ph-main" :style="`background-color: ${bgColor};
  font-family: ${fontFamily}; font-size: ${fontSyze}; ${getStyle}`">
    <h2 class="ph-title"><icon name="back2" size="5em" color="black"/> {{pagename}}</h2>
    <div class="ph-header-right">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import Icon from "./extra/Icon"
export default {
  name: 'PageHeader',
  components: {
    Icon
  },
  props: {
    pagename: {
      type: String,
      default: ''
    },
    styles: {
      type: Object,
      default: () => ({})
    },
    bgColor: {
      type: String,
      default: '#cdd1ce'
    },
    fontSyze: {
      type: String,
      default: '16px'
    },
    fontFamily: {
      type: String,
      default: 'Tahoma'
    }
  },
  computed: {
    getStyle: function () {
      return Object.entries(this.styles).map(function (key) {
        return `${key[0]}:${key[1]}`
      }).join(";")
    }
  }
}
</script>

<style>
.ph-main {
  overflow: hidden;
  background-color: #f1f1f1;
  padding: 4px 10px;
  margin-bottom: 4px;
}

.ph-main > h2 {
  float: left;
  color: black;
  text-align: center;
  text-decoration: none;
  font-size: 18px;
  line-height: 1px;
  font-weight: bold;
  font-family: Tahoma;
}

.ph-header-right {
  float: right;
  padding: 4px;
}
</style>
