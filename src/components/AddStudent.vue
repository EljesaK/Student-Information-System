<template>
  <div>
    <form @submit="addStudent">
      <input type="text" name="title" v-model="title" placeholder="Add Student">
      <button type="submit">Add Student</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddStudent",
  data () {
    return {
      id:'',
      name: "",
      dob:"",
      municipality:""
    }
  },
  methods: {
    addStudent(e){
      e.preventDefault();
      const newStudent = {
        id: this.id,
        name: this.name,
        dob: this.dob,
        municipality:this.municipality
      };
      if (newStudent.name !== ''){
        this.$emit('add-student-event', newStudent);
      }
      this.name = ''
    }
  }
}
</script>