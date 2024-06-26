<template>
  <button class="bg-gray-600 hover:bg-gray-400 border rounded px-5 py-2" :disabled=cursor-not-allowed>
    <slot />
    </button>
</template>

<script>
export default {
  data() {
    return {
      processing: false
    };
  },
}
</script>

<style>

</style>