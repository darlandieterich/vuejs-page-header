<template>
  <div class="ph-main" :style="`background-color: ${bgColor};
  font-family: ${fontFamily}; font-size: ${fontSyze}; ${getStyle}`">
    <h2 class="ph-title">
      <div class="ph-main-item">
        <icon v-on:click="test" name="back1" size="2em" color="danger"/>
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
  },
  methods: {
    test() {
      alert('hi')
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

.ph-main-item {
  float: left;
  height: 15px;
  padding: 1px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.ph-header-right {
  float: right;
  padding: 4px;
}
</style>
