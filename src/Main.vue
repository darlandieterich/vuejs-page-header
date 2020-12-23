<template>
  <div id="app">
    <pageheader pagename="Página x" :fontFamily="'Tahoma'" @clickBack="test" icon="back1">
      hello
    </pageheader>
  </div>
</template>

<script>
import pageheader from "./PageHeader"
export default {
  name: 'App',
  components: {
    pageheader
  },
  data () {
    return {
    }
  },
  methods: {
    test() {
      alert("the callback is pressed")
    }
  }
}
</script>

<style>
body {
  margin: 0px;
  padding: 0px;
}
</style>
