<template lang="">
  <div class="h-100 w-100">
    <iframe
      @load="setIframeLoaded()"
      class="iframe-scale iframe-border-none btn-fade"
      frameborder="0"
      allow="fullscreen; geolocation;"
      :class="{
        'd-none': !loaded,
      }"
      :src="url"
      title="Story Map"
    ></iframe>
    <div
      class="flex-column h-100 text-center text-white justify-content-center"
      :class="{ 'd-none': loaded, 'd-flex': !loaded }"
    >
      <div class="h1">{{ url }}</div>
      <div class="mt-4">
        <font-awesome-icon class="fa-2x" :icon="['fas', 'spinner']" spin />
      </div>
    </div>
  </div>
</template>
<script>
import { mapGetters, mapMutations } from "vuex";

export default {
  components: {},
  data() {
    return {
      loaded: false,
    };
  },
  props: {
    url: {
      type: String,
      required: true,
    },
  },
  watch: {},
  computed: {
  },
  methods: {
    setIframeLoaded() {
      console.log("iframe loaded");
      setInterval(() => {
        this.loaded = true;
      }, 0);
    },
  },
};
</script>
<style lang="scss" scoped>
.iframe-scale {
  width: 100%;
  height: 100%;
}

.popup-iframe {
  padding: 0;
  height: 60vh;
  width: 60vw;
  z-index: 99999 !important;
}
</style>
