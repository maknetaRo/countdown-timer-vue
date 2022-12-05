<template>
  <div class="home">    
    <NewYearsCounter />
  </div>
</template>

<script>
// @ is an alias to /src
import NewYearsCounter from '@/components/NewYearsCounter.vue';

export default {
  name: 'HomeView',
  components: {
    NewYearsCounter
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>

