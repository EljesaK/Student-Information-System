<template>
  <div>
    <form  class="m-5 justify-content-left col" @submit="editStd">
      <input type="text" name="id" :value="editStudent.id" class="m-3 p-2 form-control col" ref="id">

      <div class="row text-danger">
        <input type="text" name="name"  class="mt-3 mb-3 p-2 form-control col" ref="name" :value="editStudent.name">
        <input type="text" name="dob"  class="m-3 p-2 form-control col" ref="dob" :value="editStudent.dob">
      </div>
      <input type="text" name="municipality"  id="" ref="municipality"  class="form-control m-3 ms-0 me-5 p-2" :value="editStudent.municipality">
      <button type="submit" class="d-block mt-3 ps-5 pe-5 btn btn-danger row form-control" @click="$bvModal.hide('modal-3'),show()">
        Save changes
      </button>
    </form>
  </div>
</template>
<script>


export default {
  props: ["editStudent"],
  data(){
    return {
      name:"",
      dob:"",
      municipality:"",
      edit :false,
      id:""
    }
  },
  methods:{
    // eslint-disable-next-line vue/no-dupe-keys
    editStd(){

      this.name=this.$refs.name.value;
      this.dob=this.$refs.dob.value;
      this.municipality=this.$refs.municipality.value;
      this.id=this.$refs.id.value;
      alert(this.name+this.dob+this.municipality+this.id);

      const studentItem = {
        name: this.name,
        id: this.id,
        dob: this.dob,
        municipality:this.municipality
      };

      this.$emit('edit-student-item', studentItem);
      this.title='',
      this.dob='',
      this.municipality='',
      this.id='',
      this.edit=false

    },
    show(){

    }

  },


}
</script>