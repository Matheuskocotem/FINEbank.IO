<template>
    <section class="header-section">
        <section class="user-info">
            <h1 class="welcome">Hello Tanzir</h1>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
            <path d="M13 17L18 12L13 7" stroke="#9F9F9F" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M6 17L11 12L6 7" stroke="#9F9F9F" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
        </section>
      <h1> ola mundo</h1>
    </section>
  </template>
  
  <script lang="ts">
  
  export default {
    name: 'Header',
  };
  </script>
  
  <style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');
 
.header-section {
    margin-left: 40px; 
    padding: 20px;
  }

  .Welcome{
    color: var(--Default-Black, #191919);
    font-family: Inter;
    font-size: 24px;
    font-style: normal;
    font-weight: 700;
    line-height: 28px;
  }

  </style>
  