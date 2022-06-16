# vue2-youtube-embeder

## [demo](https://airmanxtw.github.io/vue2-youtube-embeder/)

## Usage
```javascript
import vue2YoutubeEmbeder from 'vue2-youtube-embeder';
import 'vue2-youtube-embeder/dist/vue2-youtube-embeder.css';
Vue.use(vue2YoutubeEmbeder);
```

## style
```html
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
```

## example 1
```html
<div class="videoContainer">
  <vue2-youtube-embeder
    src="https://www.youtube.com/embed/LOxxhecSHQM"
    title="GOBELINS"
    autoplay
    loop
  >
  </vue2-youtube-embeder>
</div>
``` 

# example 2
```html
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
```
