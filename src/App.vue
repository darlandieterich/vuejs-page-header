<template>
  <div id="app">
    <pageheader pagename="pagina x">
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
  }
}
</script>

<style>
body {
  margin: 0px;
  padding: 0px;
}
</style>
