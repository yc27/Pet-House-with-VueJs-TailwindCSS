<template>
  <div id="app" class="bg-gray-200 h-screen">
    <Nav />
    <router-view />
  </div>
</template>

<script>
import Nav from './components/Nav.vue'

export default {
  name: 'App',
  components: {
    Nav
  }
}
</script>
