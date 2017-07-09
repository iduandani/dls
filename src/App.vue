<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
body,html{
  height: 100%;
  background: #646464;  
}
#app{
  height: 100%
}


</style>
