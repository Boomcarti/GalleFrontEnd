<template>
    <div class="signup-container">
      <div class="signup-wallpaper">
        <!-- Background Image -->
        <img class="background-image" src="../assets/signupwallpaper.jpg" alt="Background" />
      </div>
      <div class="signup-form">
        <!-- Logo -->
        <img class="uct-logo" src="../assets/uctlogo.png" alt="UCT Logo" />
        <h1>Welcome back!</h1>
        <p>Please enter your details</p>
  
        <!-- Form -->
        <form @submit.prevent="submitForm">
          <div class="form-group">
            <label for="username">Username</label>
            <input
              type="text"
              id="username"
              v-model="username"
              placeholder="Username"
              required
            />
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input
              type="password"
              id="password"
              v-model="password"
              placeholder="Password"
              required
            />
            <a href="#" class="forgot-password">Forgot password?</a>
          </div>
          <button type="submit" class="login-button">Log in</button>
        </form>
  
        <footer class="footer-text">
          Powered by Galle
        </footer>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "SignUp",
    data() {
      return {
        username: "",
        password: "",
      };
    },
    methods: {
      submitForm() {
        // Handle the form submission here
        this.$router.push({name: 'Home'})
      },
    },
  };
  </script>
  
  <style scoped>
  .signup-container {
    display: flex;
    height: 100vh;
    justify-content: flex-end;
    align-items: center;
    position: relative;
  }
  
  .signup-wallpaper {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    z-index: -1;
  }
  
  .background-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  
  .signup-form {
    background-color: white;
    border-radius: 10px;
    padding: 40px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    width: 350px;
    margin-right: 80px;
  }
  
  .uct-logo {
    width: 100px;
    margin-bottom: 20px;
  }
  
  h1 {
    font-size: 24px;
    margin-bottom: 10px;
  }
  
  p {
    color: grey;
    margin-bottom: 20px;
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  input {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
  }
  
  .forgot-password {
    display: block;
    text-align: right;
    margin-top: 5px;
    font-size: 12px;
    color: #999;
  }
  
  .login-button {
    width: 100%;
    padding: 10px;
    background-color: #ff6f00;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
  }
  
  .login-button:hover {
    background-color: #ff8b00;
  }
  
  .footer-text {
    margin-top: 20px;
    font-size: 12px;
    color: #999;
  }
  </style>
  