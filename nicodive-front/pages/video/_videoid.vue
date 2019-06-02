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
