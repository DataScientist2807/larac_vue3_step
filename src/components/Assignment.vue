<template>
  <li>
    <label>
      {{ theAssignment.name }}
      <input type="checkbox" v-model="theAssignment.complete" />
    </label>
  </li>
</template>

<script>
export default {
  name: "Assignment",
  data() {
    return {
      theAssignment: this.assignment,
    };
  },
  props: {
    assignment: Object,
  },
};
</script>

<style>
</style>