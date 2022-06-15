<template>
  <div>
    <h1>example 1</h1>   
    <div
      style="
        display: flex;
        width: 100%;
        height: 320px;
        flex-direction: column;
        background-color: white;
        overflow: hidden;
        border-radius: 15px !important;
      "
    >
      <vue2-youtube-embeder
        src="https://www.youtube.com/embed/LOxxhecSHQM"
        title="GOBELINS"
        autoplay
        loop
      ></vue2-youtube-embeder>
    </div>
    <div>bottom</div>
  </div>
</template>
<script>
import Vue2YoutubeEmbeder from "@/components/Vue2YoutubeEmbeder.vue";
export default {
  components: {
    Vue2YoutubeEmbeder,
  },
};
</script>