<template>
  <div>
    <b-form-input list="my-list-id"></b-form-input>

    <datalist id="my-list-id">
      <option>Manual Option</option>
      <option v-bind:key="size" v-for="size in sizes">{{ size }}</option>
    </datalist>
  </div>
</template>

<script>
  export default {
    name: "SearchBox",
    data() {
      return {
        sizes: ['Small', 'Medium', 'Large', 'Extra Large']
      }
    }
  }
</script>

/* TODO: call API:
* https://api.openweathermap.org/geo/1.0/direct?q=Budapest&limit=5&appid=eb978d87450039215931b254857202d7
*/
