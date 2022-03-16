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
        <StdItem  v-bind:student="student"></StdItem>
      </tr>
      <tr v-bind:key="student.id" v-for="student in students">
        <td>{{ student.id }}</td>
        <td>{{student.name}}</td>
        <td>{{student.dob}}</td>
        <td>{{student.municipality}}</td>
        <td>
          <a href="#" class="edit" title="Edit" data-toggle="tooltip"><i class="fas fa-pen text-warning"></i></a>
          <a href="#" class="delete" title="Delete" data-toggle="tooltip"><i class="fas fa-trash text-danger"></i></a>
        </td>
      </tr>

    </table>

  </div>
</template>

<script>
import StdItem from "./StdItem";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Students",
  props: ["students"],
  components: {
    StdItem
  }
}
</script>