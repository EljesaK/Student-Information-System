<template>
  <div class="login">
<!--    <div class="container">-->
<!--      <div class="col-5">-->
<!--        <h3 class="row text-dark m-5">Student Information System</h3>-->
<!--        <div class="row">-->
<!--          <div class="bg-light m-5 mt-0">-->
<!--            <div class="col">-->
<!--              <div class="rounded-circle bg-primary">-->
<!--                Hello-->
<!--              </div>-->
<!--              <h4 class="text-primary">Log In</h4>-->

<!--            </div>-->
<!--          </div>-->
<!--        </div>-->
<!--      </div>-->
<!--    </div>-->
    <div class="container border-2 rounded-3">
      <div class="row row justify-content-md-center" >
        <div class="col-sm-6 col-md-4 col-md-offset-4">
          <h1 class="text-center login-title m-3">Login</h1>
          <div class="bg-muted ">
            <img class="profile-img rounded-circle " src="https://lh5.googleusercontent.com/-b0-k99FZlyE/AAAAAAAAAAI/AAAAAAAAAAA/eu7opA4byxI/photo.jpg?sz=120"
                 alt="">
            <form class="form-signin p-4">
              <input type="text" class="form-control m-3 border-bottom" placeholder="Email" required autofocus>
              <input type="password" class="form-control m-3 border-bottom" placeholder="Password" required>
              <button class="btn btn-lg btn-primary btn-block m-3" type="submit">
                Login</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>