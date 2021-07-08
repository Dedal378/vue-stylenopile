<template>
  <div class="container" id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Main from '@/components/Main'

export default {
  name: 'App',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    Header, Main
  }
}
</script>

<style lang="scss">
.container {
  display: grid;
  grid-template-columns: 60px repeat(auto-fill, minmax(60px, 100vw));
  gap: 20px;
  height: 100vh;
  overflow-y: hidden;
}
</style>
