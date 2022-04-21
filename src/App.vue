<template>
  <div id="app">
    <header class="d-flex justify-content-between align-items-center">
      <LogoComp/>
      <SelectComp 
      @selectFunction="selectedFunction"
      />
    </header>
    <main>
      <div class="container">
        <MusicsComp
        :valore="this.selectedValue"
        />
      </div>
    </main>
  </div>
</template>

<script>
import "bootstrap";
import LogoComp from "./components/LogoComp.vue";
import SelectComp from "./components/SelectComp.vue";
import MusicsComp from "./components/MusicsComp.vue";

export default {
  name: 'App',
  data(){
    return {
      selectedValue:'',
    }
  },
  components: {
    LogoComp,
    MusicsComp,
    SelectComp,
  },
  methods: {
    selectedFunction( testo ) {
      console.log(testo);
      this.selectedValue = testo;
      console.log(this.selectedValue);
    }
  },
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
  height: 100vh;
  overflow: auto;
}

</style>
