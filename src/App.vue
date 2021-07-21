<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
  </div>
</template>

<script>
import SearchBar from './Components/SearchBar.vue';
const API_KEY= 'AIzaSyBe2EDLUpvzC6lp8wmUEZAE22vLcWVvWiw';
export default {
  name: 'App',
  components: {
    SearchBar,
  },
  methods: {
    onTermChange(searchTerm) {
      console.log(searchTerm);
    },
  },
};
</script>
