<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view></router-view>
    <loading ref="loading"></loading>
  </div>
</template>

<script>
import Loading from '@/components/loading/Loading'
export default {
  name: 'app',
  components: {Loading},
  created() {
    this.$router.beforeEach((to,from,next)=>{
      this.$refs.loading.start()
      next()
    });
    this.$router.afterEach((to,from)=>{
      setTimeout(()=>{
        this.$refs.loading.finish()
      },1000)
    })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
