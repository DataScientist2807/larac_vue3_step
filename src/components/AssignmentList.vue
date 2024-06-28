<template>
  <div>
    <section v-show="assignments.length">
      <h2 class="font-bold mb-2">{{ title }}
        <span>({{ assignments.length }})</span>
      </h2>

      <AssignmentTags 
        :initial-tags="assignments.map(a => a.tag)"
        :currentTag="currentTag"
        @change="currentTag = $event"></AssignmentTags>
      <ul class="border border-gray-600 divide-y divide-gray-600 mt-6">
        <Assignment
          v-for="assignment in filteredAssignments"
          :key="assignment.id"
          :assignment="assignment"
        ></Assignment>
      </ul>
    </section>
  </div>
</template>

<script>
import Assignment from "./Assignment.vue";
import AssignmentTags from "./AssignmentTags.vue";

export default {
  name: "AssignmentList",
  components: { Assignment, AssignmentTags },
  data () {
    return {
      currentTag: 'all'
    }
  },
  props: {
    assignments: Array,
    title: String,
  },
  computed: {
    
    filteredAssignments() {
      if (this.currentTag === 'all') {
        return this.assignments;
      }
      return this.assignments.filter(a => a.tag === this.currentTag)
    }
  }
};
</script>

<style>
</style>