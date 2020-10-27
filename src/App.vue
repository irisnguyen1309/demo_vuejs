<template>
  <div id="app">
    <search @on-search-student="searchStudent($event)"/>
    <ul>
      <li v-for="student in students" :key="student.studentId">
        {{student.name}}
      </li>
    </ul>
  </div>
</template>

<script>
import Search from "./components/Search"
export default {
  name: 'app',
  data () {
    return {
      students : [
        {
          studentId: "18211TT0001",
          name: "Đức Duy",
          dateOfBirth: "01/01/2000"
        },
        {
          studentId: "18211TT0002",
          name: "Minh Tiến",
          dateOfBirth: "01/01/2000"
        },
        {
          studentId: "18211TT0003",
          name: "Quỳnh Hương",
          dateOfBirth: "01/01/2000"
        },
      ]
    }
  },
  methods: {
    searchStudent(studentName) {
      this.students = this.students.filter(student => student === studentName);
    }
  },
  // computed: {
  //   filteredStudents: function() {
  //     var self = this;
  //     return this.students.filter(function(student) {
  //       return (
  //         student.name.toLowerCase().indexOf(self.search.toLowerCase()) >= 0
  //       );
  //     });
  //   },
  // },
  components: { Search },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
