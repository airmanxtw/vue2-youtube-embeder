<template>
  <div>
    <h1>example 1</h1>
    <div class="videoContainer">
      <vue2-youtube-embeder
        src="https://www.youtube.com/embed/LOxxhecSHQM"
        title="GOBELINS"
        autoplay
        loop
      >
      </vue2-youtube-embeder>
    </div>
    <hr />
    <h1>example 2</h1>
    <div class="videoContainer">
      <vue2-youtube-embeder
        src="https://www.youtube.com/embed/dRVkQsZFISU"
        title="鳥的故事"
        autoplay
        loop
      >
        <template v-slot:button="event">
          <button v-on="event">全螢幕撥放</button>
        </template>
      </vue2-youtube-embeder>
    </div>
    <hr style="margin-top:500px" />
    <h1>example 3</h1>
    <img src="https://images1.epochhk.com/pictures/132713/120210220929100445@1200x1200.jpg" loading="lazy">

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
<style>
.videoContainer {
  display: flex;
  width: 100%;
  height: 320px;
  flex-direction: column;
  background-color: white;
  overflow: hidden;
  border-radius: 15px !important;
}
</style>