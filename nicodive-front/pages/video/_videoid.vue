<template>
  <section class="container">
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
    console.log(videoID)
    const { data } = await axios.get(VIDEO_API_URL + videoID)
    return { resp: data }
  }
}
</script>
