<template>
  <div>
    <div class="container c1">
      <h3><b>Where in the world?</b></h3>
      <button class="toggle"><fa icon="moon" />Dark Mode</button>
    </div>
    <div class="container c1">
      <div class="form-c1">
        <i><fa class="search-icon" icon="magnifying-glass" /></i>
        <input type="text" placeholder="Search For Country..." />
      </div>
      <div class="drop1">
        <div class="drop2">
          <p>Filter By Region</p>
          <button><fa icon="chevron-down" /></button>
        </div>
        <div class="drop3">
          <p>Africa</p>
          <p>America</p>
          <p>Asia</p>
          <p>Europe</p>
          <p>Oceania</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      countryInfo: [],
      url: 'https://restcountries.com/v2/all',
    }
  },
  async created() {
    const res = await this.$axios.$get(this.url)
    this.countryInfo = res
  },
}
</script>
