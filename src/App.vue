<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>


export default {
  name: 'app',
  components: {
  }
}
</script>

<style>
* {
    margin: 0
}
body {
    font-family: 'xingyan';
}
@font-face {
    font-family: 'xingyan';
    src: url('./assets/font/xingyan.eot');
    src: url('./assets/font/xingyan.eot?#iefix') format('embedded-opentype'),
        url('./assets/font/xingyan.woff') format('woff'),
        url('./assets/font/xingyan.ttf') format('truetype'),
        url('./assets/font/xingyan.svg#svgFontName') format('svg');
   
}
@font-face {
    font-family: 'pingfang';
    src: url('./assets/font/pingfang.eot');
    src: url('./assets/font/pingfang.eot?#iefix') format('embedded-opentype'),
        url('./assets/font/pingfang.woff') format('woff'),
        url('./assets/font/pingfang.ttf') format('truetype'),
        url('./assets/font/pingfang.svg#svgFontName') format('svg');
}
</style>
