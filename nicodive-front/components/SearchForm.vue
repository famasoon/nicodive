<template>
  <div class="field has-addons">
    <div class="control">
      <input v-model="name" type="text" class="input" placeholder="Search" />
    </div>
    <div class="control">
      <nuxt-link
        :to="{ name: 'result-slug', params: { slug: name } }"
        ,
        class="button is-info"
      >
        GO
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      name: ""
    }
  }
}
</script>
