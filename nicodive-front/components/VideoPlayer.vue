<template>
  <div class="video-container">
    <iframe
      allowfullscreen
      frameborder="0"
      :src="'http://embed.nicovideo.jp/watch/' + videoid"
    />
  </div>
</template>

<script>
export default {
  props: ["videoid"]
}
</script>

<style scoped>
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
  width: 70%;
  height: 70%;
}
</style>
