<template>
  <nav
    class="navbar has-shadow is-spaced"
    role="navigation"
    aria-label="main navigation"
  >
    <div class="navbar-brand">
      <a class="navbar-item" href="https://nicodive.net">NICODIVE</a>
    </div>
    <div class="navbar-end">
      <div class="navbar-item">
        <search-form />
      </div>
    </div>
  </nav>
</template>

<script>
import SearchForm from "~/components/SearchForm.vue"

export default {
  name: "NavBar",
  components: {
    SearchForm
  }
}
</script>
