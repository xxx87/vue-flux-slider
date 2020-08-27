<template>
  <v-container>
    <vue-flux :options="vfOptions" :images="vfImages" :transitions="vfTransitions" :captions="vfCaptions" ref="slider">
      <template v-slot:preloader>
        <flux-preloader />
      </template>

      <template v-slot:caption>
        <flux-caption />
      </template>

      <template v-slot:controls>
        <flux-controls />
      </template>

      <!-- <template v-slot:pagination>
        <flux-pagination />
      </template> -->

      <template v-slot:index>
        <flux-index />
      </template>
    </vue-flux>

    <button @click="$refs.slider.show('next')">NEXT</button>
    <button @click="$refs.slider.show('prev')">PREV</button>
  </v-container>
</template>

<script>
import { VueFlux, FluxCaption, FluxControls, FluxIndex, FluxPagination, FluxPreloader } from "vue-flux";
export default {
  name: "HelloWorld",
  components: {
    VueFlux,
    FluxCaption,
    FluxControls,
    FluxIndex,
    FluxPagination,
    FluxPreloader
  },

  data: () => ({
    vfOptions: {
      autoplay: true,
      delay: "5000",
      allowFullscreen: true
    },
    vfImages: ["./slides/1.jpg", "./slides/2.jpg", "./slides/3.jpg"],
    vfTransitions: [
      "blinds2d",
      "blinds3d",
      "blocks1",
      "blocks2",
      "book",
      "camera",
      "concentric",
      "cube",
      "explode",
      "fade",
      "fall",
      "kenburn",
      "round1",
      "round2",
      "slide",
      "swipe",
      "warp",
      "waterfall",
      "wave",
      "zip"
    ],
    vfCaptions: []
    // vfCaptions: ["Caption for image 1", "Caption for image 2", "Caption for image 3"]
  })
};
</script>
