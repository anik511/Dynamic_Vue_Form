<template>
  <div class="margin">
    <button @click="setSelectedTab('FormsList')">Form List</button>
    <button @click="setSelectedTab('AddForms')">Add Form</button>
    <component :is="selectedtab"></component>
  </div>
</template>

<script>
import AddForms from "./tabs/AddForms";
import FormsList from "./tabs/FormsList";
export default {
  name: "HelloWorld",
  components: {
    AddForms,
    FormsList,
  },
  data() {
    return {
      selectedtab: "FormsList",
      formlist: [],
    };
  },
  methods: {
    setSelectedTab(tab) {
      console.log(tab);
      this.selectedtab = tab;
      console.log(this.selectedtab);
    },
    addFormList(payload) {
      this.formlist.push(payload);
      this.selectedtab = "FormsList";
    },
  },
  provide() {
    return {
      formlist: this.formlist,
      addFormList: this.addFormList,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
