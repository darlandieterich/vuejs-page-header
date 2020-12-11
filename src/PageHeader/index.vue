<template>
  <div class="ph-main" :style="`background-color: ${bgColor} ${getStyle}`">
    <h2 class="ph-title">{{pagename}}</h2>
    <div class="ph-header-right">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PageHeader',
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
