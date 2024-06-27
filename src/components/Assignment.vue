<template>
  <li>
    <label class="p-2 flex justify-between items-center">
      {{ theAssignment.name }}
      <input type="checkbox" v-model="theAssignment.complete" class="ml-3"/>
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