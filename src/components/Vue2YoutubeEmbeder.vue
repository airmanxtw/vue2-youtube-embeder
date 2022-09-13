<template>
  <div :class="fillMode ? 'videoWrapper' : ''">
    <iframe
      ref="videoIframe"
      :width="width"
      :height="height"
      :src="youtubeSrc"
      :title="title"
      frameborder="0"
      :allow="allow"
      :allowfullscreen="allowfullscreen"
      :style="{ top: iframeTop }"          
    ></iframe>
    <div
      v-if="fillMode"
      class="foreground-text textStyle"
      :style="{ top: titleTop }"
    >
      <div v-if="!!title">{{ title }}</div>
      <div v-if="allowfullscreen">
        <slot
          name="button"
          v-bind="{
            click: () => {
              fullscreen();
            },
          }"
        >
          <button @click="fullscreen">Full Screen</button>
        </slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    width: {
      type: String,
      default: "100%",
    },
    height: {
      type: String,
      default: "700",
    },
    title: {
      type: String,
      default: null,
    },
    allow: {
      type: String,
      default:
        "accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture",
    },
    allowfullscreen: {
      type: Boolean,
      default: true,
    },
    autoplay: {
      type: Boolean,
      default: false,
    },
    loop: {
      type: Boolean,
      default: false,
    },
    src: {
      type: String,
      default: null,
    },
    iframeTop: {
      type: String,
      default: "-25%",
    },
    titleTop: {
      type: String,
      default: "5%",
    },
    fillMode: {
      type: Boolean,
      default: true,
    },
  },
  data() {
    return {
      model: false,
    };
  },
  computed: {
    youtubeSrc() {
      var url = new URL(this.src);
      var code = this.src.split("/").at(-1);
      if (this.autoplay) url.searchParams.append("autoplay", 1);
      if (this.loop) {
        url.searchParams.append("loop", 1);
        url.searchParams.append("playlist", code);
      }
      url.searchParams.append("mute", 1);
      return url.toString();
    },
  },
  methods: {
    fullscreen() {
      var e = this.$refs.videoIframe;
      if (e.requestFullscreen) {
        e.requestFullscreen();
      } else if (e.webkitRequestFullscreen) {
        e.webkitRequestFullscreen();
      } else if (e.mozRequestFullScreen) {
        e.mozRequestFullScreen();
      } else if (e.msRequestFullscreen) {
        e.msRequestFullscreen();
      }
    },
  },
};
</script>
<style scoped>
.videoWrapper {
  position: relative;
  padding-bottom: 56.25%;
  /* 16:9 */
  padding-top: 0px;
  height: 0;
}

.videoWrapper iframe {
  position: absolute;
  /* top: -25%; */
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 15px !important;
}

.foreground-text {
  position: absolute;
  top: 50%;
  left: 2%;
  width: 100%;
}

.textStyle {
  text-align: left;
  font-size: x-large;
  color: white;
}
</style>