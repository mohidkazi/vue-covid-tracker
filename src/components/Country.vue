<template>
    <div class="">
        <!-- country list will loop over this country -->
        <div class="max-w-sm rounded overflow-hidden shadow-lg m-auto">
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{{ country.Country }}</div>
          {{ timestamp }}
        </div>
        <div class="">
          <div class="inline-block bg-yellow-100 rounded-full px-3 py-1 text-sm text-yellow-700 mr-2 mb-2">Cases: {{ country.NewConfirmed }}</div>
          <div class="inline-block bg-red-100 rounded-full px-3 py-1 text-sm text-red-700 mr-2 mb-2">Deaths: {{ country.NewDeaths }}</div>
          <div class="inline-block bg-green-100 rounded-full px-3 py-1 text-sm text-green-700 mr-2 mb-2">Recovery: {{ country.NewRecovered }}</div>
        </div>
</div>
    </div>
</template>

<script>
import { DateTime } from 'luxon';

export default {
  name: 'Country',
  props: ['country'],
  computed: {
    timestamp() {
      return DateTime.fromISO(this.country.Date).toFormat('dd MMMM y, h:mm:ss');
    },
  },
};
</script>