<template>
  <div id="app">
    <Research></Research>
  </div>
</template>

<script>
import Research from './components/Research'

export default {
  name: 'app',
  components: {
    Research
  }
}
</script>

<style>
body {
      background-image: url(https://cdn.pixabay.com/photo/2019/04/10/12/40/watercolour-4117017_1280.png);
      background-size: 100%;
    }
#app {
  font-family: 'Grandstander', cursive;
  text-align: center;
  color: #050911;
  margin-top: 60px;
}
</style>
