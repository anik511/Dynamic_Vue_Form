<template>
  <div class="margin">
    <h1>Add Form</h1>
    <form @submit.prevent="submitData">
      <input type="button" value="Text fild" @click="addData('text')"><br />
      <input type="button" value="Email" @click="addData('email')"><br />
      <label for="lname">First wright Label name:</label><br />
      <input type="text" id="name" name="name" v-model="name" /><br /><br />
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>

<script>
export default {
  inject: ["addFormList"],
  data() {
    return {
      // type: "",
      name: "",
      value: "",
    };
  },
  computed: {
    
  },
  methods: {
    addData(type) {
      if(this.name !== ''){
        this.value +=`<label>${this.name}:</label><br><input type=" ${type}"><br>`;
      }
      else{
        alert("First Fill Up The Name");
      }
      this.name = '';
    },
    submitData() {
      if (this.value !=='') {
        this.addFormList(this.value);
        this.value = '';
      } else {
        alert("Did Not Add Any Thing!!");
      }

    },
  },
};
</script>

<style></style>
