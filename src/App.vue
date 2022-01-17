<template>
  <div id="app">
    <transition name="fade" mode="out-in">
      <router-view></router-view>
    </transition>
  </div>
</template>

<script>
  export default {
    name: 'app'
  }
</script>

<style>
#app {
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s ease-out;
}

.fade-enter, .fade-leave-to {
  opacity: 0;
}

#app a {
  font-weight: bold;
  color: #2c3e50;
}

#app a.router-link-exact-active {
  color: #42b983;
}
</style>
