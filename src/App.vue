<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList ></VideoList>
    {{ videos.length }}
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './Components/SearchBar.vue';
import VideoList from './Components/VideoList.vue'
const API_KEY = 'AIzaSyBe2EDLUpvzC6lp8wmUEZAE22vLcWVvWiw';
export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList
  },
  data() {
      return {
          videos: []
      }
  },
  methods: {
    onTermChange(searchTerm) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
        },
      }).then(response => {
          this.videos = response.data.items;
          console.log(response)
      })
    },
  },
};
</script>
