<template>
  <div id="genreopt">
    <select name="musicgenre" id="" @change="selectValue($event)">
      <option value="">All</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "inputElement",
  data() {
    return {
      selectedOption: "",
    };
  },
  methods: {
    selectValue(event) {
      //console.log(event.target.value);
      this.selectedOption = event.target.value;
      this.$emit("selectedGenre", this.selectedOption);
    },
  },
};
</script>

<style>
#genreopt {
  display: flex;
  justify-content: center;
  margin-top: 1%;
}
</style>