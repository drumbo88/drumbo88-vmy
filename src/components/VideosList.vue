<template>
  <table style="width: 100%">
    <tr><td>
      <div style="max-height: 600px; overflow-y: auto; text-align: left">
        <div v-for="(course, iCourse) in courses" :key="iCourse">
          <h2>{{ course.title }}</h2>
          <div class="lesson" v-for="(lesson, iLesson) in course.lessons" :key="iLesson">
            <a @click="selectedVideo = lesson.videoId" target="_blank">
              {{ lesson.title }}
            </a>
          </div>
        </div>
      </div>
    </td><td style="min-width: 800px">
      <iframe v-if="selectedVideo" :src="videoUrl(selectedVideo)" 
        width="800" height="450" />
    </td></tr>
  </table>  
</template>

<script>
import { videoBaseUrl, courses } from "@/db.json"

export default {
  name: "VideosList",
  data: () => ({
    courses, 
    selectedVideo: null
  }),
  methods: {
    videoUrl: (videoId) => videoBaseUrl.replace('999999999', videoId)
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .lesson {
    padding: 4px;
    border: 1px solid gray;
    cursor: pointer
  }
  .lesson a {
    display: block
  }
</style>
