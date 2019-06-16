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
    <div id="videotag" class="tags is-rounded">
      <span class="tag">タグ:</span>
      <span
        v-for="(item, index) in resp.tags.tag_info"
        :key="index"
        class="tag"
      >
        {{ item.tag }}
      </span>
    </div>
    <video-player :videoid="$route.params.videoid" />
    <div id="video">
      {{ resp }}
    </div>
  </section>
</template>

<script>
import axios from "axios"
import VideoPlayer from "@/components/VideoPlayer.vue"

// TODO: Use environment url
const VIDEO_API_URL = "http://" + process.env.DOMAIN + "/v1/video/"

export default {
  components: {
    VideoPlayer
  },

  async asyncData(context) {
    const videoID = context.params.videoid
    const { data } = await axios.get(VIDEO_API_URL + videoID)
    return { resp: data }
  }
}
</script>
