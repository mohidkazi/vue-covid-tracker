<template>
  <Header />
  <div class="container">
    <router-view/>
  </div>
</template>

<script>

import Header from '@/components/Header';

export default {
  components: {
    Header,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat&family=Roboto&family=Roboto+Condensed&display=swap');

* {
  font-family: 'Roboto', sans-serif;
}
</style>