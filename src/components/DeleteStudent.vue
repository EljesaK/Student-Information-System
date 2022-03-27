<template>
  <div>
    <form  class="m-5 justify-content-left col">
      <div class="row text-danger">
        <p class="text-danger text-center"> Are you sure you want to delete this student record?</p>
        <input type="text" name="name" v-model="name"  :placeholder="student.name" readonly class="mt-3 mb-3 p-2 form-control col">
        <input type="text" name="dob" v-model="dob" :placeholder="student.dob" readonly class="m-3 p-2 form-control col">
      </div>
      <input type="text" name="municipality" v-model="municipality" id="" readonly :placeholder="student.municipality" class="form-control p-2 row">
      <button type="submit" class="d-block mt-3 ps-5 pe-5 btn btn-danger row form-control" @click="$emit('del-student-item', student.id),$bvModal.hide('modal-2')">Delete</button>
    </form>
  </div>
</template>
<script>
export default {
  props: ["student"],
  methods:{

  }
}
</script>