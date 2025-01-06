<template>
   <main>
    <section class="forgot-container">
      <p class="title">
        FINE<span class="bank">bank</span>.IO
      </p>

      <h1>Forgot Password?</h1>
      <h2>
        Enter your email address to get the <br> password reset link.
      </h2>

      <form @submit.prevent="handleRegister">
        <p class="text-base">Email Address</p>
        <input
          type="email"
          placeholder="hello@example.com"
          v-model="form.email"
          required
          aria-label="E-mail"
        />
        <button :class="['button-forgot']">
          <div class="label">{{ text }}</div>
        </button>
        <router-link to="/login" class="sign-in-here-route">
            Back to login
        </router-link>
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
      },
      text: 'Password Reset'
    };
  },
  methods: {
    handleRegister() {
      console.log('Form submitted:', this.form);
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');


main {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.forgot-container {
  display: flex;
  flex-direction: column;
  align-items: center; 
}

.title { 
    color: var(--Primary-color, #299D91);
    text-align: center;
    font-family: Poppins, sans-serif;
    font-size: 40px;
    font-style: normal;
    font-weight: 800; 
    line-height: 1;
    letter-spacing: 2px;  
}

.bank {
    font-weight: 500; 
    letter-spacing: 1.5px; 
}


h1 {
  color: var(--Black, #191D23);
  text-align: center;
  font-family: Inter;
  font-size: 24px;
  font-style: normal;
  font-weight: 700;
  line-height: 1.2; 
}

h2{
    color: var(--Gray-01, #666);
    text-align: center;
    font-family: Inter;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 22px;

}

.text-base {
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  font-weight: 500;
  line-height: 12px; /* Reduzido o espaçamento entre as linhas */
  color: var(--Black, #191d23);
  margin-bottom: 2px; /* Diminui o espaçamento entre o texto e o campo de input */
}

input {
  border: 1px solid var(--Gray-03, #b3b3b3);
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
  margin-bottom: 25px;
}

input::placeholder {
  color: var(--Gray-03, #b3b3b3);
  font-style: italic;
}

.button-forgot {
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
  margin-top: 20px;
}

.button-forgot:hover {
  background: var(--Primary-color, #299D91);
  opacity: 0.9;
}

.button-forgot:focus {
  outline: none;
  box-shadow: 0 0 5px rgba(41, 157, 145, 0.5);
}

.sign-in-here-route {
  color: var(--Gray-02, #878787);
  text-align: center;
  font-family: Inter, sans-serif;
  font-size: 16px;
  font-weight: 600;
  line-height: 24px;
  margin-top: 20px; 
  display: block; 
  text-decoration: none; 
}
</style>
