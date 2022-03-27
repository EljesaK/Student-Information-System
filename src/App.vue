<template>
<div class="">
  <div id="app">
    <Login v-on:log-in="login" v-if="!logedIn"/>
<!--    <app-header/>-->
    <div v-if="logedIn">
      <header class="bg-light">
        <div class="row pt-4 pb-4 justify-content-between m-0">
          <div class="col-5 ps-0">
            <div class="row text-primary mb-0 ps-5 ms-5">
              <i class="fas fa-book-reader  fs-1 col-2 ms-5 mb-0"></i>
              <p class="fw-bold col-4 text-start mb-0">Student <br> Information System</p>
            </div>
          </div>
          <div class="col-2 me-5">
            <div class="row">
              <p class="text-dark font-weight-boldv fs-4 col mt-2">{{username}}</p>
              <button v-on:click="logOut" class="btn btn-primary col">Log Out</button>
            </div>
          </div>
        </div>

      </header>
      <nav>
        <router-link to="/">Home</router-link> |
        <router-link to="/">Students</router-link> |
        <router-link to="/about">About</router-link> |
        <router-link to="/help">Help</router-link>
      </nav>
      <router-view/>
    </div>

  </div>
</div>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import Login  from '@/components/LogIn.vue'
export default {
  name: 'App',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    AppHeader,
    Login
  },
  data: function () {
    return {
      logedIn: true,
      username:""
    }
  },
  methods:{
    login(username){
      this.logedIn=true;
      this.username=username;
    },
    logOut(){
      this.logedIn=false;
    }
  },
}
</script>
<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #b94254;
    }
  }
}
</style>
