<template>
	<div>
		<div>
			<h2>Realizar solicitud de API la forma Vue</h2>
			<hr>
		</div>
		<div class="container row">
			<card v-for="post in allPosts" :key="post.id" :post="post" class="ml-auto mr-auto" />
			<button class="btn btn-danger" v-scroll-to="'body'">Back to top</button>
		</div>
	</div>
</template>

<script>
	import axios from 'axios'
	import card from '@/components/card'
	import {mapGetters} from 'vuex'

	export default {
		components: {
			card
		},
		data(){
			return {
				allPosts: ''
			}
		},
		/*computed: {
			...mapGetters(['posts'])
			/*allPosts(){
				return this.$store.getters.posts
			}*/
		async asyncData({store}) {
			let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts')

			return {allPosts: data}
			//store.dispatch('setPosts', data)
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

