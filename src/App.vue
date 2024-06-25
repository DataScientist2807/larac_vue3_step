<template>
  <div>
    <section v-show="assignments.filter(a => !a.complete).length">
      <h2 class="font-bold mb-2">In Progress</h2>
      <ul>
        <li v-for="assignment in assignments.filter(a => !a.complete)" 
          :key="assignment.id">
          <label
            >{{ assignment.name }}
            <input type="checkbox" v-model="assignment.complete" />
          </label>
        </li>
      </ul>
    </section>
    <section v-show="assignments.filter(a => a.complete).length" class="mt-8">
      <h2 class="font-bold mb-2 ">Completed</h2>
      <ul>
        <li v-for="assignment in assignments.filter(a => a.complete)" 
          :key="assignment.id">
          <label
            >{{ assignment.name }}
            <input type="checkbox" v-model="assignment.complete" />
          </label>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      assignments: [
        { id: 1, name: "Finish project", complete: false },
        { id: 2, name: "Read chapter 4", complete: false },
        { id: 3, name: "Turn in homework", complete: false },
      ],
    };
  },
  methods: {
    toggle() {},
  },
  mounted() {},
};
</script>

<style>
</style>
