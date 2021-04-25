<template>
  <div class="">
    <CountrySelect :countries="countries" />
  </div>
</template>


<script>
import CountrySelect from '@/components/CountrySelect';

export default {
  name: 'CountryList',
  props: ['countries'],
  components: {
    CountrySelect,
  },
}
</script>