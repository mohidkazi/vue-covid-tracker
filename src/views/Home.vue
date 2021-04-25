<template>
  <div class="home">
    Home
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {},
  data() {
    return {
      isLoading: true,
      summaryDate: '',
      summarymessage: '',
      summaryID: '',
      summaryGlobal: {},
      status: {},
      countries: [],
      loadingIcon: require('../assets/spin.gif'),
    }
  },
  methods: {
    async fetchCovidSummary() {
      const response = await fetch('https://api.covid19api.com/summary');
      const data = await response.json();
      return data;
    },
  },
  async created() {
    const covidSummary = await this.fetchCovidSummary();
    console.log(covidSummary)
  },
}
</script>
