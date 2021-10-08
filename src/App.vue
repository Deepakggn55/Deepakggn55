<template>
  <div id="app">
    <div class="test">TEST</div>
    <div class="components" @click="showComp(compname)">Show {{compname =='Images' ?"Videos":"Images"}}</div>
    <images v-if="compname == 'Images'" :imageDetails="imageDetails"></images>
    <videos v-if="compname == 'Videos'" :videoDetails="videoDetails"></videos>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      imageDetails: [],
      videoDetails: [],
      compname: 'Images'
    }
  },
  methods: {
    showImages () {
      this.imageDetails = [{"id":1,"name":"image1","description":"This image is captured in london.","url":"https://media.istockphoto.com/photos/aerial-view-of-london-and-the-tower-bridge-picture-id1265900812?b=1&k=20&m=1265900812&s=170667a&w=0&h=jOR9G-887Sh5LXygPFBIy8TIx5vCoVDm8FKISpapq-E="},
      {"id":1,"name":"image2","description":"This image is captured in london.","url":"https://media.istockphoto.com/photos/aerial-view-of-london-and-the-tower-bridge-picture-id1265900812?b=1&k=20&m=1265900812&s=170667a&w=0&h=jOR9G-887Sh5LXygPFBIy8TIx5vCoVDm8FKISpapq-E="},
      {"id":1,"name":"image3","description":"This image is captured in london.","url":"https://media.istockphoto.com/photos/aerial-view-of-london-and-the-tower-bridge-picture-id1265900812?b=1&k=20&m=1265900812&s=170667a&w=0&h=jOR9G-887Sh5LXygPFBIy8TIx5vCoVDm8FKISpapq-E="},
      {"id":1,"name":"image4","description":"This image is captured in london.","url":"https://media.istockphoto.com/photos/aerial-view-of-london-and-the-tower-bridge-picture-id1265900812?b=1&k=20&m=1265900812&s=170667a&w=0&h=jOR9G-887Sh5LXygPFBIy8TIx5vCoVDm8FKISpapq-E="}]
    },
    showVideos () {
      this.videoDetails = [{"id":1,"name":"Video1","description":"Sample Video","url":"http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"},
      {"id":1,"name":"Video2","description":"Sample Video","url":"http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"},
      {"id":1,"name":"Video3","description":"Sample Video","url":"http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"},
      {"id":1,"name":"Video4","description":"Sample Video","url":"http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"}]
    },
    showComp (id) {
      name = ''
      switch (id) {
        case 'Images': name = "Videos"
        break;
        case 'Videos': name = "Images"
        break;
      }
      this.compname = name
    }
  },
  created () {
    this.showImages()
    this.showVideos()
  },
  components: {
    images: ()  => import('@/components/Images.vue'),
    videos: ()  => import('@/components/Videos.vue')
  }
}
</script>

<style scoped>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 10px;
  }
  .test {
    font-size: 3rem;
    text-align: center;
    text-decoration: underline;
  }
  .components {
    padding-top: 2%;
    font-size: 1rem;
    cursor: pointer;
  }
</style>
