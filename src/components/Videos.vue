<template>
  <div class="videos">
		<div class="videos-tab" v-for="(data, index) in videoDetails" :key="index">
			<video width="320px" controls><source :src="data.url" type="video/mp4" class="video">
			</video>
			<div class="video-name">{{data.name}}</div>
			<div class="video-name">{{data.description}}</div>
		</div>
  </div>
</template>

<script>
export default {
	props:['videoDetails']
}
</script>

<style scoped>
	.videos {
		padding: 3%;
	}
	.videos-tab {
		width: 29.33%;
		float: left;
		margin: 2%
	}
	.video {
		width: 100%;
	}
</style>