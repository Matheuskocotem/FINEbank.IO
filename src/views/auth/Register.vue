<template>
    <main>
      <section class="register-container">
        <p class="title">
          FINEbank.IO
        </p>
  
        <p class="Create-an-account">
          Create an account
        </p>
  
        <form @submit.prevent="handleRegister">
          <p class="text-base">Name</p>
          <input
            type="text"
            placeholder="Tanzir Rahman"
            v-model="form.name"
            required
            aria-label="Name"
          />
  
          <p class="text-base">Email Address</p>
          <input
            type="email"
            placeholder="hello@example.com"
            v-model="form.email"
            required
            aria-label="E-mail"
          />
  
          <p class="text-base">Password</p>
          <div class="password-container">
            <input
              :type="isPasswordVisible ? 'text' : 'password'"
              placeholder="●●●●●●●●●●●●●●"
              v-model="form.password"
              aria-label="Password"
            />
            <button
              type="button"
              @click="togglePasswordVisibility"
              class="eye-icon"
              aria-label="Toggle password visibility"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
              >
                <path
                  d="M2 12C2 12 5 5 12 5C19 5 22 12 22 12C22 12 19 19 12 19C5 19 2 12 2 12Z"
                  stroke="#999DA3"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
                <path
                  d="M12 15C13.6569 15 15 13.6569 15 12C15 10.3431 13.6569 9 12 9C10.3431 9 9 10.3431 9 12C9 13.6569 10.3431 15 12 15Z"
                  stroke="#999DA3"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </button>
          </div>
  
          <p class="text-terms">
            By continuing, you agree to our terms of service
            <router-link to="/terms-of-service" class="text-terms-r">terms of service</router-link>
          </p>
  
          <button :class="['button-register']">
            <div class="label">{{ text }}</div>
          </button>
  
          <p class="or-sign">
            or sign up with
          </p>
  
          <button type="button" class="google-sognup">
            Continue with Google
          </button>
  
          <p class="text-base">
            Already have an account?
            <router-link to="/login">Sign in here</router-link>
          </p>
        </form>
      </section>
    </main>
  </template>
  
  <script>
  export default {
    data() {
      return {
        form: {
          name: '',
          email: '',
          password: '',
        },
        isPasswordVisible: false, 
        isActive: true,
        text: 'Register'
      };
    },
    methods: {
      handleRegister() {
        console.log('Form submitted:', this.form);
      },
      togglePasswordVisibility() {
        this.isPasswordVisible = !this.isPasswordVisible;
      },
    },
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');
  
  main {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .register-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0px;
  }
  
  .title {
    color: var(--Primary-color, #299d91);
    text-align: center;
    font-family: 'Poppins', sans-serif;
    font-size: 48px;
    font-style: normal;
    font-weight: 800;
    line-height: 32px;
    letter-spacing: 3.2px;
  }
  
  .Create-an-account {
    color: var(--Black, #191d23);
    text-align: center;
    font-family: Inter;
    font-size: 24px;
    font-style: normal;
    font-weight: 700;
    line-height: 28px;
  }
  
  .text-base {
    font-family: 'Inter', sans-serif;
    font-size: 16px;
    font-weight: 500;
    line-height: 20px;
    color: var(--Black, #191d23);
  }

  .text-terms {
    color: var(--Gray-02, #4B5768);
    font-family: Inter;
    font-size: 14px;
    font-style: normal;
    font-weight: 300;
    line-height: 20px;
}
  .text-terms-r{
    color: var(--Primary-color, #299D91);
    font-family: Inter;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px;
}
  
  input {
    border: 1px solid var(--Gray-02, #4b5768);
    border-radius: 8px;
    display: block;
    width: 100%; 
    max-width: 100%; 
    height: 22px;
    padding: 12px 16px;
    font-size: 16px;
    color: var(--Black, #191d23);
    background-color: #fff;
    transition: all 0.3s ease;
  }
  
  input:focus {
    border-color: var(--Primary-color, #299d91);
    outline: none;
    box-shadow: 0 0 5px rgba(41, 157, 145, 0.5);
  }
  
  input::placeholder {
    color: var(--Gray-03, #b3b3b3);
    font-style: italic;
  }
  
  .password-container {
  position: relative;
  display: flex;
  align-items: center;
  width: 110%; 
}
  
  .eye-icon {
    position: absolute;
    left: 390px;
    right: 7px;
    bottom: 6px;
    cursor: pointer;
    font-size: 18px;
    background: none;
    border: none;
    outline: none;
  }

  .button-register {
  background: var(--Primary-color, #299D91);
  color: var(--White, #FFF);
  border-radius: 8px;
  display: flex;
  width: 110%;
  height: 48px;
  padding: 16px 12px;
  justify-content: center;
  align-items: center;
  font-size: 16px;
  font-weight: 600;
  text-align: center;
  cursor: pointer;
  font-family: Inter;
  transition: all 0.3s ease;
  border: none;
}

.button-register:hover {
  background: var(--Primary-color, #299D91);
  opacity: 0.9;
}

.button-register:focus {
  outline: none;
  box-shadow: 0 0 5px rgba(41, 157, 145, 0.5);
}

.or-sign{
  
}

  </style>
  