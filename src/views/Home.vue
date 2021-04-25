<template>
  <main class="home" v-if="!isLoading">
    <Title :title="summaryTitle" :date="summaryDate" />

    <Card :status="summaryStatus" />

    <CountryList :countries="countries" />
  </main>
  <main v-else class="flex flex-col align-center justify-center text-center">
    <img :src="loadingIcon" alt="" srcset="" class="w-12 m-auto">
    <span class="text-red-400">loading</span>
  </main>
</template>

<script>
// @ is an alias to /src
import Title from '@/components/Title';
import Card from '@/components/Card';
import CountryList from '@/components/CountryList';

export default {
  name: 'Home',
  components: {
    Title,
    Card,
    CountryList,
  },
  data() {
    return {
      isLoading: true,
      summaryTitle: 'Global',
      summaryID: '',
      summaryMessage: '',
      summaryStatus: {},
      countries: [],
      summaryDate: '',
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
    const summary = await this.fetchCovidSummary();
    this.summaryID = summary.ID;
    this.summaryMessage = summary.Message;
    this.summaryStatus = summary.Global;
    this.countries = summary.Countries;
    this.summaryDate = summary.Date;
    this.isLoading = false;
  },
};
</script>
