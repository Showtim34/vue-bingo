<template>
  <div class="container-fluid">
    <lotto-app></lotto-app>
  </div>
</template>

<script>
import LottoApp from './components/LottoApp.vue'

export default {
  name: 'App',
  components: { LottoApp }
}
</script>

<style>
body {
  background: rgb(63,94,251);
  background: -moz-radial-gradient(circle, rgba(63,94,251,1) 0%, rgba(252,70,107,1) 100%);
  background: -webkit-radial-gradient(circle, rgba(63,94,251,1) 0%, rgba(252,70,107,1) 100%);
  background: radial-gradient(circle, rgba(63,94,251,1) 0%, rgba(252,70,107,1) 100%);
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#3f5efb",endColorstr="#fc466b",GradientType=1);

  color: #fff
}
</style>
