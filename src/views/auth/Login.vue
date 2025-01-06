<template>
    <main>
        <section class="login-container">
            <p class="title">
            FINEbank.IO
            </p>
            <form @submit.prevent="handleLogin">
                <p class="text-base">Email Address</p>
                <input
                type="email"
                placeholder="hello@example.com"
                v-model="form.email"
                required
                aria-label="E-mail"
                />

                <div class="password-header">
                    <p class="text-base">Password</p>
                    <router-link 
                        to="/forgot-password"
                        class="forgot-password-link"
                    >
                        Forgot Password?
                    </router-link>
                </div>
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
                <div class="keep-signed-in">
                    <input 
                        type="checkbox" 
                        id="keepSignedIn" 
                        v-model="form.keepSignedIn"
                    />
                    <label for="keepSignedIn">Keep me signed in</label>
                </div>
                <button :class="['button-login']">
                    <div class="label">{{ text }}</div>
                </button>
                <p class="or-sign">
                    or sign up with
                </p>

                <button type="button" class="google-signup">
                    <img 
                        src="../img/Group.svg" 
                        alt="Google Logo"
                        class="google-logo"
                    />
                        Continue with Google
                </button>
                <router-link to="/login" class="sign-in-here-route">Create an account</router-link>
            </form>
        </section>
    </main>
</template>
<script>
export default {
  data() {
    return {
      form: {
        email: '',
        password: '',
        keepSignedIn: false,
      },
      isPasswordVisible: false, 
      isActive: true,
      text: 'Login'
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
<style>
main {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.login-container {
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

.text-base {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  font-weight: 500;
  line-height: 20px;
  color: var(--Black, #191d23);
  margin-bottom: 4px;
}

input {
  border: 1px solid var(--Gray-02, #4b5768);
  border-radius: 8px;
  display: block;
  width: 400px; 
  max-width: 400px; 
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
  width: 100%;
}

.eye-icon {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
  font-size: 18px;
  background: none;
  border: none;
  outline: none;
}

.forgot-password-link {
    display: flex;
    text-align: right;
    margin-top: 5px;
    color: var(--Primary-color, #299D91);
    font-family: 'Inter', sans-serif;
    font-size: 12px;
    font-weight: 500;
    line-height: 16px;
    text-decoration: none;
    transition: color 0.3s ease;
}

.forgot-password-link:hover {
    color: #1a6d5f;
}

.password-header {
    display: flex;
    width: 400px;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 4px;
}

.forgot-password-link {
    color: var(--Primary-color, #299D91);
    font-family: 'Inter', sans-serif;
    font-size: 12px;
    font-weight: 500;
    text-decoration: none;
    transition: color 0.3s ease;
}

.forgot-password-link:hover {
    color: #1a6d5f; 
}

.keep-signed-in {
    display: flex;
    align-items: center;
    margin-top: 10px;
    font-family: 'Inter', sans-serif;
    font-size: 16px;
    margin-bottom: 8px;
    color: var(--Black, #191d23);
}

.keep-signed-in input {
    margin-right: 8px;
    width: 20px;
    height: 20px;
    flex-shrink: 0;
}

.keep-signed-in input[type="checkbox"] {
  width: 20px;
  height: 20px;
  flex-shrink: 0;
  accent-color: #299D91; 
  border: 1px solid #299D91;
  border-radius: 4px;
}

.or-sign {
  color: var(--gray-01, #999DA3);
  text-align: center;
  font-family: Inter;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px;
  margin-top: 20px;
}

.or-sign {
  position: relative;
  color: var(--gray-01, #999DA3);
  text-align: center;
  font-family: Inter;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px;
  margin-top: 20px;
}

.or-sign::before,
.or-sign::after {
  content: '';
  position: absolute;
  top: 50%;
  width: 40%;
  height: 1px;
  background-color: #4B5768;
  opacity: 0.25;
  transform: translateY(-50%);
}

.or-sign::before {
  left: -12px; 
}

.or-sign::after {
  right: -12px; 
}


.button-login {
  background: var(--Primary-color, #299D91);
  color: var(--White, #FFF);
  border-radius: 8px;
  display: flex;
  width: 100%;
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

.button-login:hover {
  background: var(--Primary-color, #299D91);
  opacity: 0.9;
}

.button-login:focus {
  outline: none;
  box-shadow: 0 0 5px rgba(41, 157, 145, 0.5);
}

.google-signup {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  width: 100%;
  height: 48px;
  padding: 12px 16px;
  background-color: var(--Gray-04, #E4E7EB);
  border-radius: 4px;
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.3s ease;
  color: var(--Black, #191d23);
  border: none;
}

.google-signup:hover {
  background-color: #d1d5db;
}

.google-logo {
  width: 24px;
  height: 24px;
  flex-shrink: 0;
}

.sign-in-here-route {
    overflow: hidden;
    color: var(--Primary-color, #299D91);
    text-align: center;
    text-overflow: ellipsis;
    white-space: nowrap;
    font-family: semibold;
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 24px;
    display: block;
    margin-top: 20px;
    text-align: center;
}

.google-signup {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    width: 100%;
    height: 48px;
    padding: 12px 16px;
    background-color: var(--Gray-04, #E4E7EB);
    border-radius: 4px;
    font-family: 'Inter', sans-serif;
    font-weight: 500;
    font-size: 14px;
    cursor: pointer;
    transition: all 0.3s ease;
    color: var(--Black, #191d23);
    border: none;
    margin-bottom: 20px; 
}

</style>