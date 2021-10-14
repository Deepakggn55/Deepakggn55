<template>
  <div class="images">
		<div class="images-tab" v-for="(data, index) in imageDetails" :key="index">
			<img :src="data.url" class="image">
			<div class="image-name">{{data.name}}</div>
			<div class="image-name">{{data.description}}</div>
		</div>
  </div>
</template>

<script>
export default {
	props:['imageDetails']
}
</script>

<style scoped>
	.images {
		padding: 3%;
	}
	.images-tab {
		width: 29.33%;
		float: left;
		margin: 2%
	}
	.image {
		width: 100%;
	}
</style>