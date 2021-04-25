<template>
  <div class="">
    <CountrySelect @get-country="getCountry" :countries="countries" />
    <div class="flex align-center justify-center text-center gap-4">
      <select @change="orderChange()" class="form-select mt-10 w-full p-3 border border-red-600 rounded bg-white shadow-lg">
      <option value="asc" default="true">Ascending</option>
      <option value="desc" >Descending</option>
    </select>

    <select class="form-select mt-10 w-full p-3 border border-red-600 rounded bg-white shadow-lg">
      <option value="CountryCode" default="true">Name</option>
      <option value="NewConfirmed" >Cases</option>
      <option value="NewDeaths" >Deaths</option>
      <option value="NewRecovered" >Recovered</option>
    </select>
    </div>
    <div v-if="isCountry" class="flex flex-col align-center justify-center text-center gap-4">
      <Country :country="newCountry" />
    </div>
    <div v-else class="flex flex-col align-center justify-center text-center gap-4">
      <Country v-for="(country, index) in countries" :index="index" :key="country.ID" :country="country" />
    </div>
  </div>
</template>


<script>
import CountrySelect from '@/components/CountrySelect';
import Country from '@/components/Country';
import _ from 'lodash';

const subject = ['code', 'cases', 'deaths', 'recovered'];

export default {
  name: 'CountryList',
  props: ['countries'],
  components: {
    CountrySelect,
    Country
  },
  data() {
    return {
      isCountry: false,
      newCountry: {},
      filter: {
        subject: 'code', // country name (code), date, cases, deaths, recovered
        orderBy: 'asc', // asc, desc
      }
    };
  },
  methods: {
    getCountry(country) {
      this.isCountry = !!country;
      this.newCountry = country;
    },
    orderChange() {
      // this.countries = _.orderBy(this.countries, [this.filter.subject], [this.filter.orderBy]);
    },
  },
};
</script>