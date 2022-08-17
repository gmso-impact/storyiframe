<template lang="">
  <div class="h-100 w-100">
    <iframe
      @load="setIframeLoaded()"
      class="h-100 w-100 iframe-border-none"
      height="100"
      width="100"
      frameborder="0"
      allow="fullscreen; geolocation;"
      :class="{
        'd-none': !loaded,
      }"
      :src="url"
      title="Story Map"
    ></iframe>

    <div
      class="flex-column h-100 text-center bg-warning text-white justify-content-center"
      :class="{ 'd-none': loaded, 'd-flex': !loaded }"
    >
      <div class="mt-4 h1">Loading...</div>
      <div class="">{{ url }}</div>
    </div>
  </div>
</template>
<script>
import { mapGetters, mapMutations } from "vuex";

export default {
  components: {},
  data() {
    return {
      loaded: false, // set to true to disable loading screen, false to enable
    };
  },
  props: {
    url: {
      type: String,
      required: true,
    },
  },
  watch: {},
  computed: {},
  methods: {
    setIframeLoaded() {
      console.log("iframe loaded");
      this.loaded = true;
    },
  },
};
</script>
<style lang="scss" scoped></style>
