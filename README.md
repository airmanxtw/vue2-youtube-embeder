# vue2-youtube-embeder

[demo](https://airmanxtw.github.io/vue2-youtube-embeder/)

## Usage
```javascript
import vue2YoutubeEmbeder from 'vue2-youtube-embeder';
import 'vue2-youtube-embeder/dist/vue2-youtube-embeder.css';
Vue.use(vue2YoutubeEmbeder);
```

## example 1
```html
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
```
