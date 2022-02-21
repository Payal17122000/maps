<template>
  <div class="box">
    <button class="forb" @click="backToHome">
      <!-- <fa icon="back" /> -->
      back
    </button>
    <div class="row">
      <div class="col-lg-6">
        <img class="imagebox" :src="countryInfo[0].flags.png" alt="not found" />
      </div>
      <div class="col-lg-6 name1">
        <h2>
          <b>{{ countryInfo[0].name }}</b>
        </h2>
        <div class="row">
          <div class="col-lg-6">
            <p class="d-inline">
              <strong> Name:</strong> {{ countryInfo[0].nativeName }}
            </p>
            <br />
            <p class="d-inline">
              <strong>Population:</strong> {{ countryInfo[0].population }}
            </p>
            <br />
            <p class="d-inline">
              <strong>Region:</strong> {{ countryInfo[0].region }}
            </p>
            <br />
            <p class="d-inline">
              <strong>Sub Region:</strong> {{ countryInfo[0].subregion }}
            </p>
            <br />
            <p class="d-inline">
              <strong>Capital:</strong> {{ countryInfo[0].capital }}
            </p>
          </div>
          <div class="col-lg-6">
            <p class="d-inline">
              <strong>Top Level Domain:</strong>
              {{ countryInfo[0].topLevelDomain[0] }}
            </p>
            <br />
            <p class="d-inline">
              <strong>Currencies:</strong>
              {{ countryInfo[0].currencies[0].name }}
            </p>
            <br />
            <p class="d-inline">
              <strong>Languages:</strong>
              {{ countryInfo[0].languages[0].name }}
            </p>
          </div>
        </div>
        <br />
        <br />
        <strong class="d-inline">Border Countries:</strong>
        <button
          v-for="countryName in countryInfo[0].borders"
          :key="countryName"
          style="
            box-shadow: 0 0 5px rgb(0 0 0 / 30%);
            padding: 5px 25px;
            margin: 5px;
          "
        >
          {{ countryName }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      countryInfo: [
        {
          topLevelDomain: [],
          currencies: [
            {
              name: [],
            },
          ],
          languages: [
            {
              name: [],
            },
          ],
          flags: {
            png: [],
          },
          borders: [''],
        },
      ],
    }
  },
  async created() {
    const res = await this.$axios.$get(
      'https://restcountries.com/v2/name/' + this.$route.params.country
    )
    this.countryInfo = res
    console.log(this.countryInfo)
  },

  methods: {
    backToHome() {
      this.$router.push('/payal')
    },
  },
}
</script>
