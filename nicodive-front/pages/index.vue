<template>
  <section id="ranking" class="container">
    <div v-for="(item, index) in resp" :key="index" class="card">
      <nuxt-link
        :to="{ name: 'video-videoid', params: { videoid: item.link } }"
      >
        <div class="card-content">
          <div class="media">
            <div class="media-left">
              <h2 class="title">{{ item.rank }}位</h2>
            </div>
            <div class="media-content">
              <p class="title is-4">
                {{ item.title }}
              </p>
            </div>
          </div>
          <div id="thumbnail" class="card-image">
            <figure class="image is-128x128">
              <img :src="item.thumbnail" alt="Ranking item thumbnail" />
            </figure>
          </div>
          <div class="content has-text-dark">
            {{ item.desc }}
          </div>
        </div>
      </nuxt-link>
    </div>
  </section>
</template>

<script>
import axios from "axios"

const RANK_API_URL = "http://localhost:8080/v1/ranking/hourly/all"

export default {
  async asyncData(context) {
    const { data } = await axios.get(RANK_API_URL)
    return { resp: data }
  }
}
</script>
