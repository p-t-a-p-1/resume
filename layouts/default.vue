<template>
  <div>
    <header class="header">
      <common-nav></common-nav>
    </header>
    <main class="main">
      <Nuxt />
    </main>
  </div>
</template>

<style lang="scss">
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  text-align: center;
  color: #2c3e50;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.header {
  position: fixed;
  top: 0;
  left: 0;
  padding-top: 50px;
  width: 300px;
  min-height: 100%;
  height: 100%;
  background-color: #2c3e50;
}

.main {
  position: relative;
  clear: both;
  text-align: left;
  margin: 15px 15px 15px 315px;
  padding: 50px 30px;
  width: calc(100% - 400px);
}
ul {
  list-style-type: none;
}
</style>

<script>
import commonNav from '../components/commonNav.vue'
export default {
  components: {
    commonNav,
  },
}
</script>
