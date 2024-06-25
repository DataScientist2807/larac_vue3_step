<template>
  <div>
    <h2 class="font-bold mb-2">Assignments</h2>
    <ul>
      <li>Finish project <input type="checkbox"></li>
      <li>Read chapter 4 <input type="checkbox"></li>
      <li>Turn in homework <input type="checkbox"></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      assignments: [
        
      ]
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
