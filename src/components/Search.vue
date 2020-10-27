<template>
  <form
    class="col-12 col-sm-10 col-md-8 cl-lg-6"
    @submit.prevent="searchStudent()"
  >
    <input
      v-model="search"
      type="text"
      class="form-control"
      placeholder="Search to-do..."
    />
  </form>
</template>

<script>
export default {
  data() {
    return {
      search: ""
    };
  },
  methods: {
    searchStudents() {
      this.$emit("on-search-student", this.search);
    }
  }
};
</script>
