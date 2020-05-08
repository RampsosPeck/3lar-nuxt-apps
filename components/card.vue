<template>
	<div>
		<div class="card text-white bg-primary mb-3" style="max-width: 18rem;">
		  <div class="card-header">POST {{ post.id }} </div>
		  <div class="card-body">
		    <p class="card-text" style="background-color: #00FFFF;"> <nuxt-link :to="{name:'posts-id', params:{id: post.id}}"> {{ post.title }} </nuxt-link> </p>
		  </div>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			post: Object
		}
	};
</script>