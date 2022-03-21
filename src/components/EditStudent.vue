<template>
  <div>
    <form  class="m-5 justify-content-left col" @submit="editStd">
      <input type="text" name="id" v-model="id" :placeholder="editStudent.id" class="m-3 p-2 form-control col">

      <div class="row text-danger">
        <input type="text" name="name" v-model="name"  :placeholder="editStudent.name" class="mt-3 mb-3 p-2 form-control col">
        <input type="text" name="dob" v-model="dob" :placeholder="editStudent.dob"  class="m-3 p-2 form-control col">
      </div>
      <input type="text" name="municipality" v-model="municipality" id=""  :placeholder="editStudent.municipality" class="form-control m-3 ms-0 me-5 p-2">
      <button type="submit" class="d-block mt-3 ps-5 pe-5 btn btn-danger row form-control" @click="$bvModal.hide('modal-3')">
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
      name:'',
      dob:'',
      municipality:'',
      edit :false,
      id:''
    }
  },
  methods:{
    // eslint-disable-next-line vue/no-dupe-keys
    editStd(e){
      e.preventDefault();
      if(this.edit===true){
        alert("ok"+ this.name);
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
        this.id='', this.edit=false
      }
    }

  },
  watch:{
    editStudent:{
      handler(){
        this.name = this.editStudent.name;
        this.dob = this.editStudent.dob;
        this.municipality = this.editStudent.municipality;
        this.id = this.editStudent.id;
        this.edit=true
      },
      deep:true
    },
      //TODO Rreguulo te njejten edhe per id, dob, municipality
    name:{
      handler(){
        if(this.name===''){
          this.edit = false;
        }
      }
    }
  }

}
</script>