<template>
  <div id="app">
    ..
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
    RetroConsole
  },
  data () {
    return {
      lines: ['one', 'two', 'three'],
      value: ''
    }
  },
  methods: {
    insere () {
      this.lines.push(this.value)
      this.value = ''
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
