<template>
  <div>
    <table class="table text-start" id="table">
      <tr>
        <th>Index</th>
        <th>Name </th>
        <th>DoB</th>
        <th>Municipality</th>
        <th>Action</th>
      </tr>
      <tr v-bind:key="student.id" v-for="student in students">

      </tr>
      <tr v-bind:key="student.id"  v-for="student in students">
        <td>{{ student.id }}</td>
        <td>{{student.name}}</td>
        <td>{{student.dob}}</td>
        <td>{{student.municipality}}</td>
        <td>
          <button  class="edit btn">
            <i class="fas fa-pen text-warning"></i>
          </button>
          <button class="delete btn">
            <i class="fas fa-trash text-danger" ></i>
          </button>
        </td>
      </tr>

    </table>

  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Students",
  props: ["students"],
  components: {

  }
}
</script>