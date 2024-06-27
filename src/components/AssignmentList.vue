<template>
  <div>
    <section v-show="assignments.length">
      <h2 class="font-bold mb-2">{{ title }}</h2>
      <ul>
        <Assignment
          v-for="assignment in assignments"
          :key="assignment.id"
          :assignment="assignment"
        ></Assignment>
      </ul>
    </section>
  </div>
</template>

<script>
import Assignment from "./Assignment.vue";
export default {
  name: "AssignmentList",
  components: { Assignment },
  props: {
    assignments: Array,
    title: String,
  },
};
</script>

<style>
</style>