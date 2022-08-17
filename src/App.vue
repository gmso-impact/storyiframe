<template>
  <div id="app" class="d-flex flex-column">
    <a
      :href="url"
      target="_blank"
      class="bg-danger text-center d-block py-3 flex-shrink-1"
    >
      <span class="text-white mr-3 font-weight-bold">Story Map URL</span
      >{{ url }}
    </a>
    <Iframe
      url="https://storymaps.arcgis.com/stories/12f39d7a57e047c8a6274e61db8df21f"
    ></Iframe>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Iframe from "./components/iframe.vue";

@Component({
  components: {
    Iframe,
  },
  data() {
    return {
      url: "https://storymaps.arcgis.com/stories/12f39d7a57e047c8a6274e61db8df21f",
    };
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
