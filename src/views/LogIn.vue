<!--<template>-->
<!--  <div class="login">-->
<!--&lt;!&ndash;    <div class="container">&ndash;&gt;-->
<!--&lt;!&ndash;      <div class="col-5">&ndash;&gt;-->
<!--&lt;!&ndash;        <h3 class="row text-dark m-5">Student Information System</h3>&ndash;&gt;-->
<!--&lt;!&ndash;        <div class="row">&ndash;&gt;-->
<!--&lt;!&ndash;          <div class="bg-light m-5 mt-0">&ndash;&gt;-->
<!--&lt;!&ndash;            <div class="col">&ndash;&gt;-->
<!--&lt;!&ndash;              <div class="rounded-circle bg-primary">&ndash;&gt;-->
<!--&lt;!&ndash;                Hello&ndash;&gt;-->
<!--&lt;!&ndash;              </div>&ndash;&gt;-->
<!--&lt;!&ndash;              <h4 class="text-primary">Log In</h4>&ndash;&gt;-->

<!--&lt;!&ndash;            </div>&ndash;&gt;-->
<!--&lt;!&ndash;          </div>&ndash;&gt;-->
<!--&lt;!&ndash;        </div>&ndash;&gt;-->
<!--&lt;!&ndash;      </div>&ndash;&gt;-->
<!--&lt;!&ndash;    </div>&ndash;&gt;-->
<!--    <div class="container border-2 rounded-3">-->
<!--      <div class="row row justify-content-md-center" >-->
<!--        <div class="col-sm-6 col-md-4 col-md-offset-4">-->
<!--          <h1 class="text-center login-title m-3">Login</h1>-->
<!--          <div class="bg-muted ">-->
<!--            <img class="profile-img rounded-circle " src="https://lh5.googleusercontent.com/-b0-k99FZlyE/AAAAAAAAAAI/AAAAAAAAAAA/eu7opA4byxI/photo.jpg?sz=120"-->
<!--                 alt="">-->
<!--            <form class="form-signin p-4">-->
<!--              <input type="text" class="form-control m-3 border-bottom" placeholder="Email" required autofocus>-->
<!--              <input type="password" class="form-control m-3 border-bottom" placeholder="Password" required>-->
<!--              <button class="btn btn-lg btn-primary btn-block m-3" type="submit">-->
<!--                Login</button>-->
<!--            </form>-->
<!--          </div>-->
<!--        </div>-->
<!--      </div>-->
<!--    </div>-->
<!--  </div>-->
<!--</template>-->




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
                <form ref="form" @submit.prevent="login()">
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
                  <input
                      type="submit"
                      class="mt-4"
                      value="Log in"
                  >
                  <input type="text" name="logedin" value="">
                </form>
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
  name: "LogIn",
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    login() {

    },
  },
};
</script>



<!--<template>-->
<!--  <div class="vue-template row justify-content-center mt-5 pt-5">-->
<!--    <form class="col-5 align-self-center">-->
<!--      <h3>Sign In</h3>-->

<!--      <div class="form-group">-->
<!--        <label>Email address</label>-->
<!--        <input type="email" class="form-control form-control-lg" />-->
<!--      </div>-->

<!--      <div class="form-group">-->
<!--        <label>Password</label>-->
<!--        <input type="password" class="form-control form-control-lg" />-->
<!--      </div>-->

<!--      <button type="submit" class="btn btn-dark btn-lg btn-block mt-5">Sign In</button>-->

<!--      <p class="forgot-password text-right mt-2 mb-4">-->
<!--        <a href="#">Forgot password ?</a>-->
<!--      </p>-->

<!--      <div class="social-icons">-->
<!--        <ul>-->
<!--          <li><a href="#"><i class="fa fa-google"></i></a></li>-->
<!--          <li><a href="#"><i class="fa fa-facebook"></i></a></li>-->
<!--          <li><a href="#"><i class="fa fa-twitter"></i></a></li>-->
<!--        </ul>-->
<!--      </div>-->

<!--    </form>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {}-->
<!--  }-->
<!--}-->
<!--</script>-->