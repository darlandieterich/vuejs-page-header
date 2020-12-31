<template>
  <div class="ph-main" :style="`background-color: ${bgColor}; font-family: ${fontFamily};
  font-size: ${fontSize}; color: ${fgColor}; height: ${height}; ${getStyle};`">
    <h2 class="ph-header-left">
      <div class="ph-main-item" v-on:click="clickBack">
        <icon class="ph-icon-cursor" v-if="icon" :name="icon" size="large" :color="fgColor"/>
      </div>
      <div class="ph-main-item">
        {{pagename}}
      </div>
    </h2>
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
    fgColor: {
      type: String,
      default: '#000'
    },
    bgColor: {
      type: String,
      default: '#cdd1ce'
    },
    fontSize: {
      type: String,
      default: '16px'
    },
    fontFamily: {
      type: String,
      default: 'Tahoma'
    },
    height: {
      type: String,
      default: '30px'
    },
    icon: {
      type: String,
      default: null,
      description: 'Define the icon'
    }
  },
  computed: {
    getStyle: function () {
      return Object.entries(this.styles).map(function (key) {
        return `${key[0]}:${key[1]}`
      }).join(";")
    }
  },
  methods: {
    clickBack() {
      this.$emit("clickBack")
    }
  }
}
</script>

<style>
.ph-main {
  overflow: hidden;
  display: flex;
  background-color: #f1f1f1;
  padding: 4px 10px;
  height: 30px;
  align-items: center;
}

.ph-header-left {
  float: left;
  text-align: center;
  text-decoration: none;
  font-size: 18px;
  line-height: 1px;
  font-weight: bold;
}

.ph-icon-cursor{
  cursor: pointer;
}

.ph-main-item {
  float: left;
  height: 1px;
  padding: 1px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.ph-header-right {
  margin-left: auto;
  height: 15px;
  padding: 1px;
  display: flex;
  align-items: center;
  justify-content: center;
  vertical-align: baseline;
}
</style>
