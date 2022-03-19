<template>
  <div class="home">
<!--    <img alt="Vue logo" src="../assets/logo.png">-->
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <div class="p-5 pt-0">
      <div class="row justify-content-between align-content-between m-3 p-4 mb-0 bg-primary rounded-top">
        <form style="border: 1px solid black;" class="col-3 rounded-pill text-start bg-light text-muted p-1 ps-3">
          <i class="fas fa-search"></i>
          <input placeholder="search" class="bg-transparent border-0 ">
        </form>

        <div class="col-3">
          <b-button v-b-modal.modal-1>Add new</b-button>
          <b-modal id="modal-1" title="Add new student" class="modal-dialog modal-dialog-centered" hide-footer>
            <AddStudent v-on:add-student-event="addStudent"/>
          </b-modal>
        </div>
      </div>
      <div class="m-3 mt-0 p-4 rounded-bottom bg-light ">
        <Students v-bind:students="students" v-on:del-student-event="deleteStudentItem" />
      </div>
  </div></div>
</template>

<script>
//import HelloWorld from '../components/HelloWorld.vue'
// export default {
//   name: 'HomeView',
//   components: {
//     HelloWorld
//   }
// }
export default {
  name: 'HomeView',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    Students,
    // eslint-disable-next-line vue/no-unused-components
    AddStudent,
  },
  data () {
    return {
      students: [
        {
          id:1,
          name: "Mergim Bajrami",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },
        {
          id:2,
          name: "Blerton Rexha",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },{
          id:3,
          name: "Abdullah Krasniqi",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },{
          id:4,
          name: "Sami Salihu",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },{
          id:5,
          name: "Visar Uruqi",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },{
          id:6,
          name: "Naim Krasniqi",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },
      ]
    }
  },
  methods:{
    addStudent(newStudent){
      console.warn("added new student");
      this.students = [...this.students, newStudent]
    },
    deleteStudentItem(id){
      this.students = this.students.filter(student => student.id !== id);
    }
  },

  watch: {
    students: {
      handler() {
        localStorage.setItem('students',JSON.stringify(this.students))
      },
      deep: true
    }
  },
  mounted() {
    if (localStorage.getItem("students")){
      this.students = JSON.parse(localStorage.getItem("students"))
    }
  }
}
import Students from "../components/Students";
import AddStudent from "../components/AddStudent";
</script>
<style>
#table td{
  padding: 5px;
}
</style>

