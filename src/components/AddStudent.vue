<template>
  <div>
    <form @submit="addStudent" class="m-5 justify-content-center col">
        <div class="row pe-1">
          <input type="text" name="name" v-model="name" placeholder="Name" class="mt-3 mb-3 p-2 form-control col">
          <input type="date" name="dob" v-model="dob" placeholder="Date of birth" class="m-3 ms-2 p-2 form-control col">
        </div>
        <select name="municipality" v-model="municipality" id="" class="form-control p-2 row">
          <option value="0" selected>Choose...</option>
          <option value="Prishtina">Prishtina</option>
          <option value="Ferizaj">Ferizaj</option>
          <option value="Mitrovice">Mitrovice</option>
          <option value="Peje">Peje</option>
          <option value="Gjilan">Gjilan</option>
          <option value="Podejeve">Podujeve</option>
        </select>
        <button type="submit" class="d-block mt-3 ps-5 pe-5 btn btn-primary form-control row" @click="$bvModal.hide('modal-1')">Save</button>
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
      console.log("added"+ this.name + this.dob + this.municipality);
      const newStudent = {
        id: Math.floor(Math.random() * 100),
        name: this.name,
        dob: this.dob,
        municipality:this.municipality
      };
      if (newStudent.name !== ''){
        this.$emit('add-student-event', newStudent);
      }
      this.name = '',
      this.id='' ,
      this.dob='',
      this.municipality=''
    },

  }
}
</script>