<template>
  <select @change="onChange()" v-model="selected" class="form-select mt-10 w-full p-3 block border border-red-600 rounded mx-auto bg-white shadow-lg">
    <option value="0" default="true">Select Country</option>
    <option v-for="country in countries" :value="country.ID">
      {{ country.Country }}
    </option>
  </select>
</template>

<script>
export default {
  name: 'CountrySelect',
  props: ['countries'],
  data() {
    return {
      selected: 0,
    };
  },
  methods: {
    onChange() {
      const country = this.countries.find((country) => country.ID === this.selected);
      this.$emit('get-country', country);
    },
  },
};
</script>