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
    <AssignmentCreate @add="add"></AssignmentCreate>
  </section>
</template>
<script>
import AssignmentList from "./AssignmentList.vue";
import AssignmentCreate from "./AssignmentCreate.vue";

export default {
  name: "Assignments",
  components: { AssignmentList, AssignmentCreate },
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
    filters() {
      return {
        inProgress: this.assignments.filter(
          (assignment) => !assignment.complete
        ),
        completed: this.assignments.filter((assignment) => assignment.complete),
      };
    },
  },
  methods: {
      add(name) {
        this.assignments.push({
          name: name,
          completed: false,
          id: this.assignments.length + 1
        });
      }
    }
};
</script>
<style>
</style>