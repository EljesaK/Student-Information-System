<template>
  <div class="login">
    <main>
      <div class="container" >
        <div class="row justify-content-center mt-5 pt-5">
          <div class="col-6" >
            <div  class="card ">
              <div class="card-header bg-primary" >
                <h1>Login form</h1>
              </div>
              <div class="card-body m-5">

                  <input class="m-2"
                      v-model="username"
                      name="username"
                      type="text"
                      placeholder="Username"
                      required
                  >
                  <br>
                  <input class="m-2"
                      v-model="password"
                      name="password"
                      type="password"
                      placeholder="password"
                      required
                  ><br>
                <p v-if="show" class="alert alert-danger" role="alert">{{msg}}</p>
                  <input
                      type="submit"
                      class="mt-4"
                      value="Log in"
                      v-on:click="submit"
                  >

<!--                <button v-on:click="submit" class="mt-4 btn">Log In</button>-->

              </div>
            </div>

          </div>
        </div>
      </div>
    </main>
  </div>
</template>


<script>
export default {
  name : "LogIn",
  props:{

  },
  data: function(){
    return{
      username:"",
      password:"",
      logedIn:false,
      msg:"",
      logedInUser:"",
      show:false,
      users: [
        {
          username: "Eljesa",
          password: "1234"
        },
        {
          username: "Eli",
          password: "12"
        },{
          username: "Filani",
          password: "34"
        }
      ],
    }
  },
  methods:{
    submit(){
      for(const user of this.users){
        if(this.username==user.username && this.password==user.password){
          this.logedIn=true;
          this.msg="You are loged in!";
          this.logedInUser=user.username;
          this.$emit('log-in', this.logedInUser);
        }
      }
      if(!this.logedIn) {
        this.msg="Incorrect user name or password!";
        this.show=true;
      }

    },
  }
}
</script>