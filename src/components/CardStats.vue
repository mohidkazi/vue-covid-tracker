<template>
  <div class="shadow-md p-10 text-center rounded" :class="bgColor">
    <h3 class="text-3xl font-bold mb-4" :class="textColor">
      {{ title }}
    </h3>
    <div class="text-2xl mb-4">
      <span class="font-bold">
        New:
      </span>
      {{ numberWithCommas(latest) }}
    </div>
    <div class="text-2xl mb-4">
      <span class="font-bold">
        Total:
      </span>
      {{ numberWithCommas(total) }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardStats',
  props: ['title', 'latest', 'total', 'bgColor', 'textColor'],
  methods: {
    numberWithCommas(integer) {
      return integer.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
    },
  },
};
</script>