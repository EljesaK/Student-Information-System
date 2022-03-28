<template>
  <div>
    <table class="table text-start" id="table">
      <tr>
        <th>Index <button class="btn" @click="sortById"><i class="fas fa-sort" ></i></button></th>
        <th>Name <button class="btn" @click="sortByName"><i class="fas fa-sort" ></i></button></th>
        <th>DoB</th>
        <th>Municipality <button class="btn" @click="sortByMunicipality"><i class="fas fa-sort" ></i></button></th>
        <th>Action</th>
      </tr>
      <tr v-bind:key="student.id"  v-for="student in students">
        <td>{{student.id}}</td>
        <td>{{student.name}}</td>
        <td>{{student.dob}}</td>
        <td>{{student.municipality}}</td>
        <td>
          <button  class="edit btn" v-b-modal.modal-3 @click="sendInfo(student)">
            <i class="fas fa-pen text-warning" ></i>
          </button>
          <button class="delete btn" v-b-modal.modal-2 @click="sendInfo(student)">
            <i class="fas fa-trash text-danger" ></i>
          </button>

        </td>
      </tr>
      <b-modal id="modal-2" title="Delete student" class="modal-dialog modal-dialog-centered" hide-footer>
        <DeleteStudent v-bind:student="selectedUser" v-on:del-student-item="delStudentMethod"/>
      </b-modal>
      <b-modal id="modal-3" title="Edit student" class="modal-dialog modal-dialog-centered" hide-footer>
        <EditStudent v-bind:editStudent="selectedUser" v-on:edit-student-item="editStudentMethod"/>
      </b-modal>
    </table>

  </div>
</template>

<script>
import DeleteStudent from "@/components/DeleteStudent";
import EditStudent from "@/components/EditStudent";


export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Students",
  props: ["students"],
  components: {
    DeleteStudent,
    EditStudent
  },
  data : function() {
return {
    selectedUser :'',
  };
},
  methods:{
    delStudentMethod(id){
      //send to parent
      this.$emit('del-student-event', id);
    },
    sendInfo(item) {
      this.selectedUser= item;
    },
    editStudentMethod(studentItem){
      // //send to parent (HomeView.vue)
      this.$emit('edit-student-event', studentItem)
    },
    sortById(){
      this.$emit('sort-by-id')
    },
    sortByName(){
      this.$emit("sort-by-name")
    },
    sortByMunicipality(){
      this.$emit("sort-by-municipality")
    }
  }
}
</script>