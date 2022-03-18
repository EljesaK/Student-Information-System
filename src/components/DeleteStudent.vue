<template>
  <div>
    <form  class="m-5 justify-content-center col">
      <div class="row">
        <input type="text" name="name" v-model="name" placeholder="Name" class="mt-3 mb-3 p-2 form-control col">
        <input type="date" name="dob" v-model="dob" placeholder="Date of birth" class="m-3 p-2 form-control col">
      </div>

      <select name="municipality" v-model="municipality" id="" class="form-control m-3 p-2">
        <option value="0" selected>Choose...</option>
        <option value="Prishtina">Prishtina</option>
        <option value="Ferizaj">Ferizaj</option>
        <option value="Mitrovice">Mitrovice</option>
        <option value="Peje">Peje</option>
        <option value="Gjilan">Gjilan</option>
        <option value="Podejeve">Podujeve</option>
      </select>
      <button type="submit" class="d-block m-3 ps-5 pe-5 btn btn-warning form-control">Delete</button>
    </form>
  </div>
</template>