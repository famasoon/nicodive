<template>
  <section class="container is-fluid">
    <h1 class="title">
      {{ resp.video.title }}
    </h1>
    <div class="tags is-rounded">
      <span class="tag">再生数: {{ resp.video.view_counter }}</span>
      <span class="tag">マイリスト数: {{ resp.video.mylist_counter }}</span>
    </div>
    <div class="notification">説明文: {{ resp.video.description }}</div>
    <div class="video-container">
      <iframe
        width="640"
        height="360"
        allowfullscreen
        frameborder="0"
        :src="'http://embed.nicovideo.jp/watch/' + $route.params.videoid"
      />
    </div>
    <div id="video">
      {{ resp }}
    </div>
  </section>
</template>

<script>
import axios from "axios"

const VIDEO_API_URL = "http://localhost:8080/v1/video/"

export default {
  async asyncData(context) {
    const videoID = context.params.videoid
    const { data } = await axios.get(VIDEO_API_URL + videoID)
    return { resp: data }
  }
}
</script>

<style>
.video-container {
  position: relative;
  padding-bottom: 56.25%; /*16:9*/
  padding-top: 30px;
  height: 0;
}

.video-container iframe,
.video-container object,
.video-container embed {
  position: absolute;
  top: 0;
  left: 0;
  width: 50%;
  height: 50%;
}
</style>
