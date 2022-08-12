<template>
  <div id="app">
    <Iframe url="https://storymaps.arcgis.com/stories/12f39d7a57e047c8a6274e61db8df21f" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Iframe from "./components/iframe.vue";

@Component({
  components: {
    Iframe,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
@import "node_modules/bootstrap/scss/bootstrap.scss";
#app {
  height: 100vh;
}
</style>
