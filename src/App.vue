<template>
  <div>
    <p>
      <input type="text" v-model="greeting" />
    </p>
    <p>{{ greeting }} {{ greeting.length }}</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      greeting: "Hello World",
    };
  },
  mounted() {
    /* alert('hello') */
    setTimeout(() => {
      this.greeting = 'Changed';
    }, 3000)
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
