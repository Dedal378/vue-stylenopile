<template>
  <div id="app" class="wrapper">
    <div class="loader lighter"></div>
    <div class="loader darker"></div>
    <div class="container">
      <Header />
      <Main />
    </div>
  </div>
</template>

<script>
import Header from '@/components/Header'
import Main from '@/components/Main'

export default {
  name: 'App',
  components: {
    Header, Main
  }
}
</script>

<style lang="scss">
.container {
  position: relative;
  display: grid;
  grid-template-columns: 60px repeat(auto-fill, minmax(calc(100vw - 120px), 1000vw));
  gap: 20px;
  max-height: 100vh;
  overflow-y: hidden;
}

.loader {
  position: absolute;
  width: 100vw;
  height: 110vh;
  opacity: 1;

  &.darker {
    background-color: #686868;
    transform: translateY(-110vh);
    animation: loader-up-down 5s cubic-bezier(.39, .39, .32, 1.19);
    z-index: 100;
  }

  &.lighter {
    background-color: #bdbdbd;
    transform: translateY(-110vh);
    animation: loader-down 5s cubic-bezier(.39, .39, .32, 1.19);
    z-index: 99;
  }
}


@keyframes loader-up-down {
  from {
    transform: translateY(-110vh);
  }
  50% {
    transform: translateY(-10vh);
  }
  to {
    transform: translateY(-110vh);
  }
}

@keyframes loader-down {
  from {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10vh);
  }
  to {
    transform: translateY(-110vh);
  }
}
</style>
