<template>
  <div class="header" :style="`margin:${margin}`">
    <h2 class="pgname">{{pagename}}</h2>
    <div class="header-right">
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
    margin: {
      type: String,
      default: '0px 0px 4px 0px'
    }
  }
}
</script>

<style scoped>
.header {
  overflow: hidden;
  background-color: #f1f1f1;
  padding: 4px 10px;
  margin-bottom: 4px;
}

.header h2 {
  float: left;
  color: black;
  text-align: center;
  text-decoration: none;
  font-size: 18px;
  line-height: 1px;
}

.header h2.pgname {
  font-size: 25px;
  font-weight: bold;
}

.header-right {
  float: right;
  padding: 4px;
}
</style>
