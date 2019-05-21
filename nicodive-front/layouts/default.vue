<template>
  <div>
    <navbar />
    <nuxt />
  </div>
</template>

<script>
import NavBar from "~/components/NavBar.vue"
export default {
  components: {
    navbar: NavBar
  }
}
</script>
