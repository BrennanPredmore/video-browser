<template>
  <div>
    <SearchBar></SearchBar>
    <Hello></Hello>
  </div>
</template>

<script>
import SearchBar from './Components/SearchBar.vue';
import Hello from './Components/Hello.vue';
export default {
  name: 'App',
  components: {
    SearchBar,
    Hello,
  },
};
</script>
