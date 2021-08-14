<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" width="100" />
    <VideosList />
  </div>
</template>

<script>
// @ is an alias to /src
import VideosList from "@/components/VideosList.vue";

export default {
  name: "Home",
  components: {
    VideosList,
  },
};
</script>
