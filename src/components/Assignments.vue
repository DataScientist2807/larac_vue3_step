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

    <form @submit.prevent="add">
      <div class="border border-gray-600 text-black">
        <input v-model="newAssignment" placeholder="New assignment" class="p-2" />
        <button type="submit" class="bg-white p-2 border-l">Add</button>
      </div>
    </form>
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

      newAssignment: ''
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
      add() {
        this.assignments.push({
          name: this.newAssignment,
          completed: false,
          id: this.assignments.length + 1
        });
        this.newAssignment = ''
      }
    }
};
</script>
<style>
</style>