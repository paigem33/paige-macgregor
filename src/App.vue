<template>
  <Header/>
</template>

<script>

import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header
  }, 
  methods: {
    scrollTo(element) {
      if (element == "home") {
        this.$router.push(`/`).catch(()=>{});
        window.scrollTo({ top: -80, behavior: "smooth" });
      } else {
        var elementPosition = document.getElementById(element).offsetTop;
        window.scrollTo({ top: elementPosition - 35, behavior: "smooth" });
        if (this.$router.history.current.path !== `/${element}`)
          this.$router.push(`/${element}`);
      }
    },
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>
