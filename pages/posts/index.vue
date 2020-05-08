<template>
	<div>
		<div>
			<h2>Realizar solicitud de API la forma Vue</h2>
			<hr>
		</div>
		<div class="container row">
			<card v-for="post in posts" :key="post.id" :post="post" class="ml-auto mr-auto" />
		</div>
	</div>
</template>

<script>
	import axios from 'axios'
	import card from '@/components/card'

	export default {
		components: {
			card
		},
		data(){
			return {
				posts: ''
			}
		},
		async asyncData() {
			let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts')
			return {posts: data}
		},
		head: {
			title: 'Lista de POST'
		}
	};
</script>

<!--
<script>
	import axios from 'axios'
	export default {
		data(){
			return {
				posts: ''
			}
		},
		asyncData(context){
			return axios.get('https://jsonplaceholder.typicode.com/posts').then(res => {
				return {posts: res.data}
			}).catch(error => {
				console.log(error)
			})
		}
	};
</script> -->

<!--
<script>
	import axios from 'axios'
	export default {
		data(){
			return {
				posts: []
			}
		},
		mounted(){
			axios.get('https://jsonplaceholder.typicode.com/posts').then(res => {
				this.posts = res.data;
				console.log(this.posts);
			}).catch(error => {
				console.log(error)
			})
		}
	};
</script>
-->

