<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">
      {{ title }}
    </h2>
    <div class="text-2xl mt-4 mb-10">
      {{ timestamp }}
    </div>
  </div>
</template>

<script>
import { DateTime } from 'luxon';

export default {
  name: 'Title',
  props: ['title', 'date'],
  computed: {
    timestamp() {
      return DateTime.fromISO(this.date).toFormat('dd MMMM y, h:mm:ss');
    },
  }
}
</script>