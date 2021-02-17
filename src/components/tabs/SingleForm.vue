<template>
  <div>
    <h1>Form List</h1>
    <form>
    <div v-html="form"></div>
    <input type="button" value="Save">
  </form>
  </div>
</template>

<script>
export default {
  props: ['form']
};
</script>

<style></style>
