<template>
  <div>
    <section>
      <h2 class="font-bold mb-2">In Progress</h2>
      <ul>
        <li v-for="assignment in assignments" :key="assignment.id">
          <label
            >{{ assignment.name }}
            <input type="checkbox" v-model="assignment.complete" />
          </label>
        </li>
      </ul>
    </section>
    <section class="mt-8">
      <h2 class="font-bold mb-2 ">Completed</h2>
      <ul>
        <li v-for="assignment in assignments" :key="assignment.id">
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
        { id: 0, name: "Finish project", complete: false },
        { id: 1, name: "Read chapter 4", complete: false },
        { id: 2, name: "Turn in homework", complete: false },
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
