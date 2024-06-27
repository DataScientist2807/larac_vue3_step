<template>
  <section class="space-y-6">
  <AssignmentList
    :assignments="filters.inProgress"
    title="in Progress"
  ></AssignmentList>
  <AssignmentList
    :assignments="filters.completed"
    title="Completed"
  ></AssignmentList>
</section>
</template>
<script>
import AssignmentList from "./AssignmentList.vue";

export default {
  name: "Assignments",
  components: { AssignmentList },
  data() {
    return {
      assignments: [
        { id: 1, name: "Finish project", complete: false },
        { id: 2, name: "Read chapter 4", complete: false },
        { id: 3, name: "Turn in homework", complete: false },
      ],
    };
  },
  computed: {
    /* inProgress() {
      return this.assignments.filter((assignment) => !assignment.complete);
    },
    completed() {
      return this.assignments.filter((assignment) => assignment.complete);
    }, */

    filters() {
      return {
      inProgress: this.assignments.filter((assignment) => !assignment.complete),
      completed: this.assignments.filter((assignment) => assignment.complete)
    }
    }
  },
};
</script>
<style>
</style>