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
        <Students v-bind:students="students" v-on:del-student-event="deleteStudentItem" v-on:edit-student-event="editStudentItemEvent" v-on:sort-by-id="sortById" v-on:sort-by-name="sortByName" v-on:sort-by-municipality="sortByMunicipality"/>
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
    Students,
    AddStudent,
  },
  data () {
    return {
      students: [
        {
          id:11,
          name: "Mergim Bajrami",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },
        {
          id:29,
          name: "Blerton Rexha",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },{
          id:13,
          name: "Abdullah Krasniqi",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },{
          id:42,
          name: "Sami Salihu",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },{
          id:27,
          name: "Visar Uruqi",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },{
          id:20,
          name: "Naim Krasniqi",
          dob:"1989-10-05",
          municipality:"Prishtine"
        },
      ],
      editStudent:{
        id:'',
        name:'',
        dob: '',
        municipality: '',
      }
    }
  },
  methods:{
    addStudent(newStudent){
      console.warn("added new student");
      this.students = [...this.students, newStudent]
    },
    deleteStudentItem(id){
      this.students = this.students.filter(student => student.id !== id);
    },
    // editStudentItem(id){
    //   //find the index of the students's id
    //   var objIndex = this.students.findIndex(obj=> obj.id === id);
    //   this.editStudent.name = this.students[objIndex].name;
    //   this.editStudent.dob = this.students[objIndex].dob;
    //   this.editStudent.municipality = this.students[objIndex].municipality;
    //
    // },
    editStudentItemEvent(studentItem){
      //find the index of this id's object
      let objIndex = this.students.findIndex(obj => obj.id === parseInt(studentItem.id))
      // //update the item
       this.students[objIndex].name = studentItem.name;
      this.students[objIndex].id = studentItem.id;
      this.students[objIndex].dob = studentItem.dob;
      this.students[objIndex].municipality = studentItem.municipality;
    },
    sortById(){
      this.students.sort(function (a, b) {
        return a.id - b.id;
      });
    },
    sortByName(){
      this.students.sort(function(a, b) {
        const nameA = a.name.toUpperCase(); // ignore upper and lowercase
        const nameB = b.name.toUpperCase(); // ignore upper and lowercase
        if (nameA < nameB) {
          return -1;
        }
        if (nameA > nameB) {
          return 1;
        }

        // names must be equal
        return 0;
      });
    },
    sortByMunicipality(){
      this.students.sort(function(a, b) {
        const nameA = a.municipality.toUpperCase(); // ignore upper and lowercase
        const nameB = b.municipality.toUpperCase(); // ignore upper and lowercase
        if (nameA < nameB) {
          return -1;
        }
        if (nameA > nameB) {
          return 1;
        }

        // names must be equal
        return 0;
      });
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

