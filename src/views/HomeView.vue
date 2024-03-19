

<template>
  <main>
    
    <section id="hero" class="d-flex align-items-center">

      <div class="container-fluid">
        <div class="row justify-content-center">
            <div class="d-none d-sm-none d-md-block col-lg-6  ">
              <img src="@/assets/logo.png" class="img-fluid " alt="">
            </div>

            
            <img src="@/assets/team.png" class="img-fluid d-block d-md-none" alt="">

          <div class=" col-lg-6 pt-3  d-flex flex-column justify-content-center">

            <h1 class='text-center'>Welcome back</h1>
            <h5 class='text-center mb-3'>Enter your email address and password to access your account</h5>
           
              <div class="col-md-12">
                <label for="inputEmail4" class="form-label">Email</label>
                <input type="text" class="form-control mb-3" v-model="email" placeholder="email">
              </div>
              
              <div class="col-12">
                <label for="inputPassword4" class="form-label">Password</label>
              <input type="password" class="form-control mb-3 " v-model="password" placeholder="Password">
              </div>
             
              <div class="col-12">
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" id="gridCheck">
                  <label class="form-check-label" for="gridCheck">
                    Remember me
                  </label>
                </div>
              </div>
              
              <div class="col-12">
                <button @click="login" class="btn btn-success text-light">Sign In</button>
              </div>

          </div>
          
        </div>
      </div>

    </section><!-- End Hero -->
  </main>
</template>


<script>
import axios from 'axios';

export default {
  name: "login",
  data() {
    return {
      email: model.email,
      password: model.password
    };
  },
  mounted(){
    this.login();
  },
  methods: {
    async login() {
     
       axios.post('/login', {
          email: this.email,
          password: this.password
        });
        
       
    }
  }
};
</script>