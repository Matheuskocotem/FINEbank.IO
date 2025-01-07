<template>
    <div>
        <Sidebar />
    </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Sidebar from '@/components/Sidebar.vue';

export default defineComponent({
  name: 'YourViewName', 
  components: {
    Sidebar, 
  },
});
</script>


<style>

</style>