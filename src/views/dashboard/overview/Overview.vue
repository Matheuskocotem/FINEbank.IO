<template>
  <section class="main-container">
    <Sidebar />
    <section class="content-area">
      <Header />
    </section>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Sidebar from '@/components/Sidebar.vue';
import Header from './components/Header.vue';

export default defineComponent({
  name: 'YourViewName', 
  components: {
    Sidebar,
    Header,
  },
});
</script>

<style scoped>
.main-container {
  display: flex;
  height: 100vh; 
}

.sidebar {
  width: 280px; 
}

.content-area {
  flex-grow: 1; 
  margin-left: 280px; 
  padding: 0px;
}
</style>
