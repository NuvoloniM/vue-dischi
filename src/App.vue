<template>
  <div id="app">
    <header>
      <LogoComp/>
    </header>
    <main>
      <div class="container">
        <div class="row"></div>
      </div>
    </main>
  </div>
</template>

<script>
import "bootstrap";
import LogoComp from "./components/LogoComp.vue";

export default {
  name: 'App',
  components: {
    LogoComp
  }
}
</script>

<style lang="scss">
@import "./assets/style/variables.scss";
@import "bootstrap/dist/css/bootstrap.min.css";
header {
  background: $primary_color;
}
main {
  background: $secondary_color;
  height: calc( 100vh - 50px);
}

</style>
