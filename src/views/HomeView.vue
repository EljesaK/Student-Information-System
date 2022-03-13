<template>
  <div class="home p-5">
<!--    <img alt="Vue logo" src="../assets/logo.png">-->
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <form action="" class="row justify-content-between align-content-between m-3 p-4 mb-0 bg-primary rounded-top">
      <div style="border: 1px solid black;" class="col-3 rounded-pill text-start bg-light text-muted p-1 ps-3">
        <i class="fas fa-search"></i>
        <input placeholder="search" class="bg-transparent border-0 ">
      </div>

      <input type="button" value="Register New Student" class="col-2 bg-light rounded-2 border-1 p-1">
    </form>
    <div class="m-3 mt-0 p-4 rounded-bottom bg-light ">
    <table class="table text-start" id="table">
      <tr>
        <th>Index</th>
        <th>Name </th>
        <th>DoB</th>
        <th>Municipality</th>
        <th>Action</th>
      </tr>
      <tr>
        <td>1458</td>
        <td>Mergim Bajrami</td>
        <td>1989-10-05</td>
        <td>Prishtine</td>
        <td>
          <a href="#" class="edit" title="Edit" data-toggle="tooltip"><i class="fas fa-pen text-warning"></i></a>
          <a href="#" class="delete" title="Delete" data-toggle="tooltip"><i class="fas fa-trash text-danger"></i></a>
        </td>
      </tr>
      <tr>
        <td>1458</td>
        <td>Mergim Bajrami</td>
        <td>1989-10-05</td>
        <td>Prishtine</td>
        <td>
          <a href="#" class="edit" title="Edit" data-toggle="tooltip"><i class="fas fa-pen text-warning"></i></a>
          <a href="#" class="delete" title="Delete" data-toggle="tooltip"><i class="fas fa-trash text-danger"></i></a>
        </td>
      </tr>
      <tr>
        <td>1458</td>
        <td>Mergim Bajrami</td>
        <td>1989-10-05</td>
        <td>Prishtine</td>
        <td>
          <a href="#" class="edit" title="Edit" data-toggle="tooltip"><i class="fas fa-pen text-warning"></i></a>
          <a href="#" class="delete" title="Delete" data-toggle="tooltip"><i class="fas fa-trash text-danger"></i></a>
        </td>
      </tr>
    </table>
    </div>



  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
//
// export default {
//   name: 'HomeView',
//   components: {
//     HelloWorld
//   }
// }
</script>
<!--<script>-->
<!--$(document).ready(function(){-->
<!--  $('[data-toggle="tooltip"]').tooltip();-->
<!--});-->
<!--</script>-->
