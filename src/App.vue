<template>
  <div>
    <!--  <button class="text-green">Click Me</button>
    <button :class="buttonClasses">Click Me</button> -->
    <!-- <button :class="buttonClasses" v-on:click="toggle">Click Me</button> -->
    <button :class="active ? 'text-red' : 'text-green'" @click="toggle">Click Me</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      /* buttonClasses: "text-green", */
      active: false,
    };
  },
  methods: {
    toggle() {
      /* alert('toggle'); */
      /* this.buttonClasses = 'text-red' */
      this.active = !this.active;
    },
  },
  mounted() {},
};
</script>

<style>
html,
body {
  height: 100%;
}
body {
  display: grid;
  place-items: center;
}
.text-red {
  color: red;
}
.text-green {
  color: green;
}
</style>
