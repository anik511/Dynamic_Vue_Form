<template>
  <div class="margin">
    <SingleForm v-for="(form,index) in formlist" :key="index" :form="form"/>
  </div>
</template>

<script>
import SingleForm from "./SingleForm";
export default {
  components: {
    // SingleForm,
    SingleForm,
  },
  inject: ["formlist"],
  data() {
    return {};
  },
};
</script>

<style></style>
