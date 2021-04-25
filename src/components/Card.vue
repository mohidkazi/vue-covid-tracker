<template>
  <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-3 xs:ml-4 xs:mr-4 md:ml-0 md:m-0">
    <CardStats title="Cases" :latest="status.NewConfirmed" :total="status.TotalConfirmed" bgColor="bg-yellow-200" textColor="text-yellow-600" />
    <CardStats title="Deaths" :latest="status.NewDeaths" :total="status.TotalDeaths" bgColor="bg-red-200" textColor="text-red-600" />
    <CardStats title="Recovered" :latest="status.NewRecovered" :total="status.TotalRecovered" bgColor="bg-green-200" textColor="text-green-600" />
  </div>
</template>

<script>
import CardStats from '@/components/CardStats';

export default {
  name: 'Cards',
  components: {
    CardStats,
  },
  props: ['status', ]
};
</script>